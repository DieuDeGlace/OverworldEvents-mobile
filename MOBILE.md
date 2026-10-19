# OverworldEvents mobile

Derived from [OverworldEvents](https://github.com/DieuDeGlace/OverworldEvents), upstream main at 0b2f339. Original history, authorship, license and SDK attribution are retained. A separate repository is used because GitHub does not allow a same-owner fork.

This is a Windows x64 mod for the Steam game running in GameNative. The only mobile algorithm change is executable validation: the tested stripped Steam image has timestamp 0x5d93ab0d and SizeOfImage 0x58a000. MobileBuild.h names that identity; immutable validation is cached. Encounter, native marker, dungeon and reward rules are unchanged. Individual native hooks still check their instruction signatures.

Install one OverworldEvents.dll in the actual Steam game Mods folder. Use a CubeMegaMod build with the OverworldEvents bridge (upstream 9cffebd or newer). Preserve existing OverworldEvents.state and all progression/save files. Close the game and back up before updating. Removing this DLL disables its hooks on the next launch; restoring old DLLs does not undo terrain already generated with different rules.

Build with CMake using clang-cl in a Windows x64 Visual Studio SDK environment. All eight upstream rules/state/assets/instance/travel/health/object/town tests passed for this mobile source on 2026-10-18. These tests do not prove all encounter types or generated dungeons work in live gameplay. Device integration results are recorded in the release notes.

No game binaries, saves, Steam login data or Microsoft runtimes are included.
