# Agent-64-Spies-Never-Die-VR-Mod
VR Mod for Agent 64: Spies Never Die v1004

AGENT 64 VR  -  VR mod for "Agent 64: Spies Never Die" (Unity 2020.3.49f1, IL2CPP x64)
====================================================================================

Version 0.1.5 (test build on Quest 3).

Only used in solo play, haven't test online

WHAT IT DOES
------------
* Full stereo VR through OpenXR (SteamVR, Meta/Oculus, Virtual Desktop, WMR...).
* Head tracking. The view is anchored on the game camera, and your real movement is added on top.
* The first-person weapon is moved into your VR hand. Shots, and "use" rays, go where the hand points.
* The VR controllers drive the game's own actions (Forward, Attack, Interact, Menu...).
  They are merged into the game's input system, so your keyboard and mouse keep working too.
* The HUD and menus appear on a floating screen. In menus you point at the screen with the gun hand
  and click with its trigger, like a mouse.
* The game's own camera (crosshair, doors / "use", shots, your in-game body) is turned toward
  where your gun hand points, through the game's mouse-look controls (GameAim = Hand / Head / Off).
* Turning: the right stick snap-turns (or smooth-turns) your VR view, and the left stick always
  walks where you are looking (or where your left hand points - MovementDirection).

INSTALL
-------
1. Copy the BepInEx folder from this zip into the game folder (next to the game's .exe) and let it merge.
   You should end up with   BepInEx\plugins\A64VR\A64VR.dll   and   BepInEx\plugins\A64VR\OpenXR.dll
3. Start SteamVR (or your OpenXR runtime), then launch the game.

To disable Mod: rename winhttp.dll to winhttp.dll.bak or  win http.dll  (or set enabled = false in doorstop_config.ini).

CONTROLS (right-handed default)
-------------------------------
Right trigger ........ Attack (fire)

Left trigger ......... Secondary (aim mode / zoom) (not tested)

A .................... Interact (use / open / confirm)

B .................... Reload, and Cancel / back in menus

Y .................... Menu (pause)

X .................... Score / objectives

Right grip ........... Glaive "the laser sight is shown while held"

Left grip ............ Next gadget

Left stick ........... Move (and navigate menus)

Right stick L/R ...... Snap turn (SnapTurn = false for smooth turn)

Right stick up/down .. Next / previous weapon (scroll in menus)

Left stick click ..... Tap: hide / show the floating screen during gameplay

Both stick clicks .... Re-centre the view

Menus: point with the right hand, click with the right trigger.

CONFIG  -  BepInEx\config\agent64.vr.cfg  (created on first launch; edits apply live)
-------------------------------------------------------------------------------------
[Controls]  which VR control presses each game action, e.g.  Reload = MainGrip
            (Main... = gun hand, Off... = other hand; add :tap or :hold; comma = any of them)
            
[General]   GameAim (Hand / Head / Off), GameAimPitch, GameAimResponse,
            LeftHanded, SnapTurn / SnapTurnAngle / SmoothTurnSpeed, TurnMode (VR / Game),
            MovementDirection (Head / OffHand / Game), MirrorToDesktop
[Camera]    EyeHeightOffset, WorldScale (if the world feels too big or too small), AnchorSmoothing

[Weapons]   WeaponInHand, AimWithHand, AimRotationOffset, GunModelPositionOffset / RotationOffset
            (moves the gun in your hand), LaserSight / LaserButton, DisableAimAssist
[UI]        FollowMode (Lazy / Head / GunHand / OffHand), Distance, Width, LaserPointer

[Input]     StickDeadzone, MouseTurnSpeed (turn speed when TurnMode = Game),
            KeyboardFallback

TIPS
----
* Aim assist is switched off while in VR (DisableAimAssist), because it pulls shots toward
  where the game camera looks, not where your hand points.
* If the gun sits in a strange place in your hand, adjust [Weapons] GunModelPositionOffset
  (x right, y up, z forward, in metres) and GunModelRotationOffset.
* TurnMode = Game makes the right stick turn the game's own camera instead (your in-game body
  turns too); its speed is [Input] MouseTurnSpeed.

Issues
------
bullets hit enemy but the bullet trace is above you but laser point to enemy

CREDITS & LICENCES
------------------
* Agent 64: Spies Never Die belongs to its developer Replicant D6.
* OpenXR.dll (native OpenXR bridge) by Astien (c) 2025 - free, non-commercial redistribution,
  see BepInEx\plugins\A64VR\LICENSES. This mod must stay free.
* BepInEx / Il2CppInterop - LGPL 2.1. This is a fan-made, non-commercial mod.
