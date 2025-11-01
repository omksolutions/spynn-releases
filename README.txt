Spynn - Readme

This is a 5 v 5 networked football simulation game created in OpenGL (version 4.6) / GLSL and uses the DirectX XInput for gamepad / controller input.
---------------

Quick Setup:

 - Run 'SpynnServer.exe'

 - Note the Hostname / local IP
 
- Connect a gamepad (Xbox controller is ideal) but most should work

- Run 'SpynnClient.exe' which is the main game client

- Put in the server IP / hostname in the 'Server address' field (just click on the input box, it should highlight slightly and start typing it will overwrite existing values)

 - Hit 'C' to connect or click on the Connect button 

 - If connected you will see your player 'sphere' on screen and should be able to interact / kick the ball around.

 - Get another player to connect, players are assigned opposing teams in round-robin fashion by the server currently.

 - Server score and time limits can be configured via the server-config.json. Requires restart.


NOTE: The game isn't finished and probably has lots of bugs and issues. May not work great on a slow network as the physics is quite real-time.

REQUIREMENTS:

 - The demo release only targets windows currently
 - PC with graphics card capable of OpenGL version 4.6
 - A working PC compatible game pad
 - Please click 'Allow' if windows requests a firewall entry to allow traffic
 - Some PCs / Antivirus may falsely flag the executables as malware but this is not true! ignore the warning or put them on a safe list if needed.

