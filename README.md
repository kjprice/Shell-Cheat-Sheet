# Shell-Cheat-Sheet
A collection of tips for making life easier when working in a terminal

## Networking

Finding other devices on machine's subnet:
```
arp -a
```

Get machine's local IP network info:
```
ifconfig
```

To limit IP network results to find local IP address:
```
ifconfig en0 # Assumes connected to internet using en0
```

## Edit Files
```
touch filename.txt # Creates file immediately
vi filename.txt # Provides vim editor to edit file
echo "Hello" > filename.txt # Overwites file contents with "Hello"
echo "Hello" >> filename.txt # Appends file contents with "Hello"
cat > filename.txt # Allows you to type anything you want and then hit "ctrl+D" to write to file
```

## Read Files
```
cat filename.txt # Prints entire contents of file to the screen
more filename.txt # Provides VIM-like viewer to read file
less filename.txt # Like "more" but allows you to go backwards
head -n 10 filename.txt # Prints top 10 lines of file
tail -n 10 filename.txt # Prints bottom 10 lines of file
tail -f filename.txt # Prints end of file and continuously prints any new additions to file
```

## Hardware
How much memory exists and is available
```
free -h
```

How much storage exists and is available
```
df -h
```

Summary of CPU stats
```
lscpu
```

Checks the load on CPU
```
top d1
```

Check temperature of device (Raspberry Pi)
```
vcgencmd measure_temp
```

#### Hardware stats file locations

Some devices have files which include stats of hardware:

```
cat /proc/meminfo # displays details about the memory.
cat /proc/partitions # reveals the size and number of partitions on your SD card or HDD.
cat /proc/version # shows you which version you are using.
```

## Processes

Show all processes running in the background
```
ps aux
```

List process(es) listening to port 9999
```
lsof -i :9999
```

## Intermittent Connection Problems (SSH Console Blanking)

See if `power save enabled` is outputed from running the following line:

```sh
dmesg
```

If so, then disable power save. Edit the config file `sudo nano /etc/rc.local`, and add the line:

```sh
setterm -blank 0 -powerdown 0 -powersave off || true
```

Additionally, you can verify if your machine is being throttled by running:

```sh
vcgencmd get_throttled
```
