# TRI TOWERS 2 (g_tri_towers_2)

Status: **playable** — the first Unity-family port: start screen, deals, card play, music and sound.
GameId 286, 1024×768, Unity 3.2. Facts: [notes/scaffold.md](notes/scaffold.md).

## Checklist
- [x] Starts: `make run GAME=g_tri_towers_2` (player log on stdout)
- [x] Graphics and text look right
- [x] Sound and music (FMOD → PulseAudio through libmega_unity.so)
- [x] Launcher settings: language, window size, player count, upgrades and challenges from
      Data/settings_gamedata.xml are read
- [ ] `AllPlayersLoggedIn` still not found (log spam each frame; sign-in text only)
- [ ] A full game to the end screen, verified by hand
- [x] Launcher messaging (FIFO/TCP to the cabinet) failing doesn't break play

## Log
- 2026-10-07 — First Unity game. The cabinet's LinuxPlayer runs unchanged on the shared runtime
  with 5 libraries from the cabinet (GLU, curl 3, FMOD Ex, Theora, gthread). Needed: Data/ next
  to the player's real path (hard link in player/), the launcher.xml the loader wrote (keys found
  in AMIUnityExtensions_Plugins.dll and LauncherFile.dll strings), and FMOD forced from OSS (10)
  to PulseAudio (13). Played by hand: works, sound plays.
