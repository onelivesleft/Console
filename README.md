# Console

A Console module to add textual commands to your Tabletop Simulator mods, generally for debugging.  ```console.ttslua``` provides the basics needed to add commands to your games, and ```console++.ttslua``` is an example module which adds a full debug system for accessing and monitoring your program's structure.


### console.ttslua

Console module, allows you to add commands to your Tabletop Simulator mods.  Commands are prefixed by a ```>``` (though
you can change this to w/e you want).  You can also add validation functions to check the messages
players are sending.  

Built-in console commands:
* ```help/?```  Lists available commands or provides information on specified command
* ```info```    Displays help on all available commands.  Alias for ```help -all```
* ```alias```   Creates an alias of another command with preset parameters
* ```echo```    Display text
* ```cls```     Clear console text
* ```=```       Evaluates the specified expression
* ```cmd```     Enter command mode: no longer required to type ```>``` before commands
* ```exit```    Exit command mode
* ```>```       Type this on its own to toggle command mode

Main functions it gives you access to:
* ```console.add_validation_function``` Adds a validation function all chat will be checked against
* ```console.add_player_command```      Adds a command any player can use
* ```console.add_admin_command```       Adds a command only admins can use


### console++.ttslua

Example module demonstrating how to use the base module, though this is a useful debug tool in its own
right and will become more feature-rich over time.  

The runtime envirorment is treated like a filesystem, allowing you to view and access global variables.
Included commands:
* ```ls/dir```      List tables, variables, objects and functions at your current location or location specfied.
* ```cd```          Change the table you are currently located in.  
* ```cd..```        Change the table you are currently located in to its parent.
* ```add```         Add a variable or table.
* ```set```         Set the variable specified to the value specified.
* ```tgl/toggle```  Toggle the boolean variable specified.
* ```rm/del```      Remove the variable specified.
* ```call```        Call the function specified.  You may then store the result with ```set``` or ```add```.
* ```~```           Display result of most recent function call or expression evaluation.
* ```exec```        Execute a series of commands.
* ```watch```       Watch a variable or object; display it if it changes.
* ```shout```       Broadcast a message to all players

All commands in console++ except ```shout``` are locked to admin players only.
Also includes simple swear-word blocking message validation.

[Tutorial](http://blog.onelivesleft.com/2017/09/debugging-your-tts-mods-with-console.html)

### Installation

If you are using Atom with the TTS plug-in then put ```console.ttslua``` and ```console++.ttslua``` in folder  ```<your user folder>/Documents/Tabletop Simulator/Console```, and then in your code you can simply write ```#include Console/console``` or ```#include Console/console++``` (be sure to enable the ```#include``` feature in the package settings).

If you're using a different editor then you can simply paste the code for ```console.ttslua``` into your own.  If you want to use ```console++.ttslua``` then paste it below that, and remove the ```#include console``` it starts with.
