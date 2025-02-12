# Building the Plugin/Mod

## Prerequisites

* Java 21
* Maven (`mvn`)
* You need to compile [Spigot][1] first and add it to your local Maven repo.
* You may or may not need to compile [WorldGuard][2] and add it to your local Maven repo.

## Build

Step by step:

```bash
$ git submodule update --init --recursive
$ ./gradlew tasks
$ ./gradlew shadowJar
$ ./gradlew jar_windows_amd64
```

The plugin can be found at `bukkit/build/libs/CienmaMod-Bukkit-*.jar`.
The mod can be found at `fabric/build/libs/cinemamod-windows_amd64-*.jar`.

To build mods for different platforms, replace `windows_amd64` with other architecture pairs, such as `linux_amd64` and `macos_arm64`.

Note that `tasks` task is mandatory as it would trigger the necessary process to fetch external resources.

## Appendix A - Compiling Spigot

Use `BuildTools.jar` to deploy a workspace first. 

```bash
$ java -jar BuildTools.jar --rev 1.21.4
```

Navigate to `Spigot` and run `mvn install`

```bash
$ cd Spigot
$ mvn install
```

[1]: https://www.spigotmc.org/wiki/buildtools/
[2]: https://github.com/EngineHub/WorldGuard

