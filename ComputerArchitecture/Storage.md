# Storage

## Magnetic disk

### Access Time
There's three type of access time of magnetic disk:
* **Seek Time**: Move the read-write head to the track of data.
* **Rotational latency**: Also known as "rotational delay". After the read-write head moved to the track, it has to wait for the disk rotate to the sector, which contains the data it need.
```
Average rotation time = 0.5 * (1/rotation speed)
```
* **Transfer Time**: The time to access a sector, which relates on size of sector, rotation speed and density of track.

In general, Seek Time >> Rotational latency >> Transfer Time.

The total access time of a disk is Seek Time + Rotational latency + Transfer Time.
