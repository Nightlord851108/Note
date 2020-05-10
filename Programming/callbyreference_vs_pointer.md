# Call by Reference vs Pointer

## Question from my classmate.
- Friend: [FB post](https://www.facebook.com/groups/1403852566495675/permalink/2614127808801472/)
- Friend: hey, bro
- Friend: may i ask you what's the difference between call by reference and call by value with a pointer argument in C++?

## Ans

Through call by reference, you're actually editing the same variable, while
passing a pointer through call by value, you're not.<br/>
In the pointer approach, you actually get a new variable which contains the
same value of the address to the caller.

The easiest way to understand the difference is:
```
int foo(int &a) {
   a = 3;
}
```
```
int foo(int *a) {
   a = &3;
}
```
The two code segments above are quite different. For the first function, since
it's called by reference, a simple copy assignment could effect the original
variable from the caller; for the second function, through the copy assignment,
the only variable effected here is the local variable "a" in this function,
nothing will be changed to the original variable from the caller.

Somebody, from the comments, say that pointer is more dangerous, however, it's
only to the starters who's not familiar with pointer, in my opinion.<br/>
Someone claim that call by reference is more easier and convenient, and I agree
with that.

In my opinion, it doesn't worth a lot to compare the two concepts in c/c++
language, since it's quite obvious during the implementation.<br/>
However, the concept is quite important in almost all other languages, come
after c/c++, especially for javascript.<br/>
It's because, almost all other languages after c/c++, using only called by
value concept, and all the variables, which contain objects, are actually
pointers. Unknowing this concept could cause some basic bugs which are quite
hard to be discovered.

The reason I said it's especially important for javascript is that, nowadays, several javascript framework are normally used to develop a web page. It's common to use data binding with an javascript object or array variable. Without knowing this concept, a programmer will simply use some thing like:

```
arr = [];
```

to clear an array. At first, it seems correct, be cause the value of arr has
been changed to an empty array; however, you'll find the view does not updated
accordingly, the data binding seems not working. The reason is the data binding
here, is actually binding the array store in the variable "arr", not binding
the variable "arr". Once we use copy assignment here, as I said, all variables
of array or object are pointers in Javascript, the value we're really changing
is the address record in the variable "arr", instead of the array that "arr"
pointed to. As the result, the data binding will never be triggered by the
statement.<br/>
The better approach here could be:
```
while (arr.length > 0) {
  arr.pop();
}
```
which is modifying the original array.

This is the most common bug I've seen, which is due to passing a
pointer argument through called by value.


## Further Questions
- Friend: Very appreciated.
- Friend: It’s a really clear elaboration.
- Friend: I agree with the author say, “It is doesn’t worth a lot to compare the two concepts in C++”
- Friend: However, I still has some questions.

1. It is almost the same for 
```
int foo(isn’t &a){
  a=3;
}

int foo(int *a){
  *a=3;
}
```
right?

### Ans
To the execution purpose, yes, they can reach the same goal. 
However, since their concepts are different basically, their's a slightly different in resource using. Since pointer is called by value, it's definitly using more resources than called by reference, since called by reference uses nearly no resource.
But, again, it's not really worth to compare, since the copy of an address is just an 4 bytes, or 8 bytes, according to the OS, which is reaaly not a big deal in a modern computer; this might be worth in some embedded system, though.

- Friend: 2. For the JavaScript’s demonstration, it means we only overwrite the “reference(pointer)” point to the variable and we don’t actually change the target variable it self,right. And if it will lead to the memory leak?

### Ans
Actually, it's not that easy to reach a memory leak in a language after Java, since almost all modern languages introduced garbage collector, which will release all the memories the program can no longer reach.
But in this case, it's a similarly concept of memory leak. Yes, since we used "arr = []", we're no longer able to access the data binding array with the variable; however, this doesn't mean it caused a memory leak, although the concept is similar. 
1. Since the framework still hold the reference of the array, it doesn't match the definition of memory leak. And the framework may provide API to get the array, in that case, the similar concept would also be gone.
2. The dangerous of memory leak is that while the program's executing, the unused occupied memory kept increasing through the life time. However, in this case, the unreachable memory would be stable, since I can only lost a reference to a data binding variable, thus, the problem here will not be as dangerous as memory leak; the main problem is that it would cause some bugs among updating.


- Friend: Sorry for I have few experience working on JavaScript. I will be very appreciative If you can give me further explains.
### Ans
Don't be, there's no reason for anyone to be familiar with all programming languages. 
It's hard to explain the situation of bugs in Javascript, though, it would be better to understand when you face the problem some day in the future.
