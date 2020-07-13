# Dark Reign 2

## General Update:
- Fixed issue with Direct Input buffer filling up and causing mouse cursor to freeze.
- Fixed issue with path planning failing to resolve in time due to calculation per tick limits.
- Altered path planning to make units herd together instead of creating an annoying single file and getting caught behind each other.
- Fixed issue where saving stats would cause the game to crash.

## OpenGL Update:
- Implementation of OpenGL rendering instead of DirectX 7 (Currently in progress)
- 4k resolution is possible by setting a breakpoint at the `create device` error and following the code manually...
- More information in the `upgrade-graphics-system` branch of this project.

## Todo (In Progress Development)
- NAT Loopback (Hairpinning) for users on a local network to mix with online players.
- Locking / Unlocking (Generally updating) a created game may cause the IP to be reset to the `Local IP` set in multiplayer options for people not currently in the game.
- Join / Create a private lobby.
- Music doesn't work.
- Map transfers fail to initiate.
- Online: Games created by a user may become stuck if that user leaves the room while another player is attempting to join.
- Game sometimes locks up at the end of a multiplayer match.
- Unit path-finding is still a major controversy amongst players and will need to be resolved for enjoyment of newer players.

## Fixed (Check Releases Section)
- Private Rooms: Users can now join private rooms if they know the password ;)

- Fixed issue where a user could join a room that they're already in.
- Fixed issue where a user could join a room but not be connected.
- Fixed issue with MINT Lobby login authentication failing in some cases.
- Fixed issue with player list not updating in MINT Lobby.
- Fixed issue with game list not updating correctly when joining a room.
- Fixed issue where [Save Stats] could crash the game when attempting to record stats at the end of match.

- Online: New password would always be accepted when signing up / updating account even if they didn't match.
- Online: Communication with lobby would lock up during some requests causing a noticeable delay (for example game creation) before they finally resolved.
- Online: Fixed issue with certain characters in a username causing authentication to fail.
- Online: Change password workflow implemented.
- Online: Added more detail regarding login error messages so players can determine what caused their account to fail to login.

## Prior Release (Patch 1.3)

### Bug Fixes:

1. Fixes problem with 6 or more players trying to startup a multiplayer game and the game disappearing from the list after the 5th player has joined the game, if map was chosen before all players entered game.

2. Fixes problem with 8 or more players being able to start a multiplayer game.

## Prior Release (Patch 1.1)

### Bug Fixes:

1. Fix to line of sight to correct Lightning Tower not being able to attack in certain situations.
2. Fixed flyers to move more smoothly and path plan better... especially though urban environments.
3. Fixes to beam effects to correctly show them when created under shroud (fence beams, artillery etc).
4. Fix for a crash created by several people in the WON lobbies switching rooms.
5. Fix for "unresolved transporter" crash.
6. Changes to the way the redbook audio device is found to help with multiple CD-Rom drives.
7. Changes to handle packet corruption in multiplayer (cheating attempts / denial of service).
8. Fix for intermittent "illegal var name" crash.
9. Upgraded to the latest WON library to fix various problems.
10. Building footprint & traction type / surface type changes to improve air unit pathing over pipes.
11. Change to prevent interpolation while stalled (units flying into the air).
12. Fixed boat Range bug, which allowed certain boats to fire much farther than expected.
13. Fixes to aspects of Strategic AI (some of these would have lead to some of the stalls in the AI which prevent it from constructing).
14. Minor problems in bombardier system (air strikes and mojos).
15. Building placement bugs.
16. Money allocation bug which occurred when higher priority items displaced lower priority items (the usage of the lower priority item was not refunded which resulted in that item not being built for a long time).
17. Clamped the maximum range defense would attempt to maximize enemy threat (this lead to the AI believing that the gun towers in your base were threatening its base and it would send every available unit to that location).
18. Interface vars which point at READONLY vars cannot be modified (this was the source of one of the cheats found by players).

---

### New Improvements:

1. Addition of status icons for low performance (simulation, display and networking).  If your performance drops below a certain level it will notify you if the drop is caused by your CPU, your video card, or your net connection.
2. Added frame advance when performance drops so player doesn’t feel game has locked up.
3. Added a few more checks for cheating prevention.
4. Change to allow low detail lights.
5. Clear player selection when joining a game (so chat isn't locked onto a player once you're in the room).
6. Addition of 'Resource Configuration' in Multiplayer / Instant Action setup. This will allow you to set whether all Resources will regenerate or not.
7. Changes to layout in WON lobby.
8. Addition of ignore functionality in WON lobby.
9. Addition of player icons for ignored / muted and moderator.
10. Added new key-bindings:

```
e - select all units on map
l - leave (unload) transport
shift r - recycle
h - cycle through HQ’s
d - drop map marker
c - activate comms menu

squad ai behaviors
alt s - scout
alt k - skirmisher
alt d - defender
alt w - warrior
alt t - terminator
```

11. Sped up the Pre-Post fire animations on several units to make them react faster.
12. Decreased speed and LOS on Construction Rigs to help reduce the chance of a ‘Turret Rush’.
13. Reduced rotation of Scorpion tank turret to 180 degrees.
14. Several tweaks to the Baron Samedi to make it more effective.
15. Several other minor balance tweaks.
16. Improvements to Strategic AI:

- Builds a lot more gun towers (defensive personality builds more than aggressive).
- Builds multiple facilities when cash is available.
- Builds water and air units when applicable.
- Addition of OrdererLevel manifest in construction system (which is used for GunTowers, primary rigs).
- When adjusting the difficulty level of an AI it also multiplies the incoming money that AI gets (hard x2 brainsick x4 and easy /2).
- Improved use of disruptors around the base.
- Tweaked the monetary allocations for defensive and aggressive.
- Gun towers are recycled when recycling a refinery where the resource has been exhausted.
- The rigs the AI gets from recycling facilities are now reused.

17. Added support for language specific auto updated patches.
18. New patches need only be the actual RTP patch file (no need for redistributing the patch installer and the RTPatch DLL as these have been added to the games data via the 1.1 patch).
19. Added axes, which allow symmetrical painting of textures and colors on maps.
20 Linked buildings (like public telepads) now display their link in the studio and also there was a bug in the studio, which prevented you from changing a telepad link once it had been set.
21. If any player has different data they are notified at game start so that they need not wait for the OOS message.
22. Made the OOS message more confrontational giving the player to exit immediately.
