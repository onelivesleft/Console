# TTSConsole

A Console module to add textual commands to your games, generally for debugging.  
Download into a Console folder in your TTS #include directory and enable the #include feature to 
allow you to add ```#include Console/console``` or ```#include Console/console++``` to your code,
or simply paste the source into your code if you dont want to use the #include feature.

*console.ttslua*:
```#include Console/console```
Console module, allows you to add commands to your games.  Commands are prefixed by a '>' (though
you can change this to w/e you want).  You can also add validation functions to check the messages 
players are sending.  

Built-in commands:
* ```help/?```  Lists available commands or provides information on specified command
* ```cmd```     Enter command mode: no longer required to type '>' before commands
* ```exit```    Exit command mode
* ```>```       Type this on its own to toggle command mode

*console++.ttslua*: 
```#include Console/console++```
Example module demonstrating how to use the base module, though this is a useful debug tool in its own 
right and will become more feature-rich over time.  If you want to use this by copy-pasting it into your
code then paste it below where you paste console.ttslua, and remove the #include line.

The runtime envirorment is treated like a filesystem, allowing you to view and access global variables.
Included commands:
* ```cd```   Change the table you are currently located in.  
* ```ls/dir```   List all tables and variables at your current location or location specfied.
* ```set```  Set the variable specified to the value specified.
* ```tgl/toggle``` Toggle the boolean variable specified.
* ```rm/del```   Remove the variable specified.
* ```add``` Add a variable or table
* ```shout``` Broadcast a message to all players

All commands except ```shout``` are locked to admin players only.
