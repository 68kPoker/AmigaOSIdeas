
GameX is an Application Programming Interface for Amiga OS.

It offers the reimplementation of many original functions from Amiga shared libraries, namely:

- CreateUpfrontLayer() - creates a new Layer,
- MoveLayer() - moves Layer,
- SizeLayer() - changes Layer size,
- UpfrontLayer() - brings Layer to front,

- RegionToCR() - internal function, converts Region to ClipRect list.

WARNING: You must not mix these Layer (and other) functions with the system ones unless stated otherwise!

System graphics and user-interface API is rich, thus there isn't much need for new functions.

The GameX takes advantage of high Blitter speed on aligned-blits.

- OpenWindowTagList() - opens window,

The user-interface input is reimplemented using own input.device handler, and output using nicer graphics
calls.

More tags are provided to customize interface:
WA_NewLook, /* Set a look of your window */

LOOK_CLASSIC, /* classic Amiga OS 1.3 look */
LOOK_NEW, /* Amiga OS 2.0/3.0 look */
LOOK_CUSTOM /* Custom look */

The double-buffering is handled using DBufInfo, and the buffer-sync region is calculated.

The features and more recognized tags will be added. Also the BOOPSI gadget mechanism - with respect
to double-buffering (own classes must be built).

The main program loop handles double-buffering messages (and Copper interrupt on line 0) and also
responds to the IDCMP messages. New IDCMP message is sent when there is a need to update screen buffer
when in double-buffering.

Additional topics:
- Blitter objects (BOBs),
- audio.device channel allocation, sounds and music replaying,
- gameport.device joystick handler,
