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
```