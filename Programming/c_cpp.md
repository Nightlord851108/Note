# Programming：
### C++ call by value
When an object is pass to a function/method by value, it'll call copy constructor.

### enum:
The **enum** in c-lang is mostly used for status.
Initially, the first item of the enum list will be zero, and the rest increase by 1 in sequence.

Exaple1:
```
enum GameStatus
  {
      Menu,
      Loading,
      Playing,
      Pause,
      GameOver
  };
  printf("%d\n", Menu);
  printf("%d\n", Loading);
  printf("%d\n", Playing);
  printf("%d\n", Pause);
  printf("%d\n", GameOver);
```
The console output will be:
```
0
1
2
3
4
```

If we specified a number to one of the item, then the following items will be the numbers increased by 1 according to the specified number.

Exaple2:
```
enum GameStatus
  {
      Menu,
      Loading,
      Playing=5,
      Pause,
      GameOver
  };
  printf("%d\n", Menu);
  printf("%d\n", Loading);
  printf("%d\n", Playing);
  printf("%d\n", Pause);
  printf("%d\n", GameOver);
```
The console output will be:
```
0
1
5
6
7
```

## For loop
If the condition of for loop is empty, it's equivalent to while(true);

## String
#### The length of string will be 1 less than the length of char array, since there'll be a '\0' character put to the end of the string.

### strcmp
#### Compare between two string
The implementation of strcmp should be similar to following code:
```
int strcmp(str1, str2) {
    int result = 0;
    for (int i = 0; i < sizeof(str1)/sizeof(char); ++i) {
        result = str1[i] - str2[i];
        if (result != 0) {
            return result;
        }
    }
    return result;
}
```
Therefore, the result of strcmp will be the value of the difference between the first-different-pair-characters of the two strings, for example, the result of strcmp('Hello', 'World') would be: 'H' - 'W' = 15.

### strcat
#### Combine the second string to the first string, and return the reference of the first string.
Example:
```
char s1[20]
char s2[20]
strcpy(s1, "google");
strcpy(s2, "apple");
char *s3 = strcat(s1, s2);
printf("strcat result1: %s\n", s1);
printf("strcat result2: %s\n", s2);
printf("strcat result3: %s\n", s3);

strcpy(s3, "Hello, world");

printf("strcat result4: %s\n", s1);
printf("strcat result5: %s\n", s3);
```
The console output will be:
```
strcat result1: googleapple
strcat result2: apple
strcat result3: googleapple
strcat result4: Hello, world
strcat result5: Hello, world
```
