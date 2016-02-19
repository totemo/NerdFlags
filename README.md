NerdFlags
=========
WorldGuard custom flags for the Reddit Public Minecraft servers.

Available flags:

| Flag Name             | Type                  | Default Value | Description |
|-----------------------|-----------------------|---------------|-------------|
| date                  | String                | *N/A*         | Creation date of the region (arbitrary string). |
| created-by            | String                | *N/A*         | Creator name of the region (arbitrary string). |
| entry-commands        | String                | *N/A*         | Commands to run on region entry, separated by '|'. |
| weather               | State                 | DENY          | Allow or deny weather in the region. |
| compass               | State                 | ALLOW         | Allow or deny teleportation with the compass. |
| allow-drops           | State                 | ALLOW         | Allow or deny dropped items (e.g. from mining). |
| allow-mob-drops       | State                 | ALLOW         | Allow or deny mob or player death drops. |
| player-mob-damage     | Set&lt;EntityType&gt; | {}            | The set of mob types protected from player damage. |
| nether-portal         | State                 | ALLOW         | Allow or deny teleportation through nether portals. |
| end-portal            | State                 | ALLOW         | Allow or deny teleportation through end portals. |
| snowball-firefight    | State                 | DENY          | Allow or deny snowballs extinguishing fire. |
| warp                  | Location              | *N/A*         | Teleport a player to the specified location on region entry. |
| use-dispenser         | State                 | ALLOW         | Allow or deny player interaction (right click) with a dispenser. |
| use-note-block        | State                 | DENY          | Allow or deny player interaction (right click) with a note block. |
| use-workbench         | State                 | ALLOW         | Allow or deny player interaction (right click) with a workbench. |
| use-door              | State                 | ALLOW         | Allow or deny player interaction (right click) with a door. |
| use-lever             | State                 | ALLOW         | Allow or deny player interaction (right click) with a lever. |
| use-pressure-plate    | State                 | ALLOW         | Allow or deny player interaction with a pressure plate. |
| use-button            | State                 | ALLOW         | Allow or deny player interaction (right click) with a button. |
| use-jukebox           | State                 | ALLOW         | Allow or deny player interaction (right click) with a jukebox. |
| use-repeater          | State                 | DENY          | Allow or deny player interaction (right click) with a repeater. |
| use-trap-door         | State                 | ALLOW         | Allow or deny player interaction (right click) with a trap door. |
| use-fence-gate        | State                 | ALLOW         | Allow or deny player interaction (right click) with a fence gate. |
| use-brewing-stand     | State                 | ALLOW         | Allow or deny player interaction (right click) with a brewing stand. |
| use-cauldron          | State                 | ALLOW         | Allow or deny player interaction (right click) with a cauldron. |
| use-enchantment-table | State                 | ALLOW         | Allow or deny player interaction (right click) with a enchantment table. |
| use-ender-chest       | State                 | ALLOW         | Allow or deny player interaction (right click) with a ender chest. |
| use-tripwire          | State                 | ALLOW         | Allow or deny player interaction with a trip wire. |
| use-beacon            | State                 | ALLOW         | Allow or deny player interaction (right click) with a beacon. |
| use-anvil             | State                 | ALLOW         | Allow or deny player interaction (right click) with an anvil. |
| use-comparator        | State                 | DENY          | Allow or deny player interaction (right click) with a comparator. |
| use-hopper            | State                 | ALLOW         | Allow or deny player interaction (right click) with a hopper. |
| use-dropper           | State                 | ALLOW         | Allow or deny player interaction (right click) with a dropper. |


Building NerdFlags
------------------
NerdFlags depends on WorldGuard Custom Flags and WorldGuard Region Events,
nether of which are available in a public Maven repository.  (The most likely
repository would be maven.mewin.de, since [mewin](https://github.com/mewin)
wrote both of these plugins.)  So, instead, NerdFlags' dependencies must be
installed in the local repository, as follows.

To install WorldGuard Custom Flags in the local repository:

1. Download the 1.8.1-beta plugin JAR from [here](http://dev.bukkit.org/bukkit-plugins/worldguard-custom-flags/).
1. Install the JAR into the repository:
```
   mvn install:install-file -Dpackaging=jar -Dfile=WGCustomFlags.jar \
     -DgroupId=com.mewin -DartifactId=WGCustomFlags -Dversion=1.8.1-beta
```

To install WorldGuard Region Events in the local repository:

1. Check out and build the latest sources (version 1.1) from GitHub:
```
   git clone https://github.com/mewin/WorldGuard-Region-Events
   cd WorldGuard-Region-Events
   mvn package
```
2. Install the JAR into the local repository:
```
   mvn install:install-file -Dpackaging=jar -Dfile=target/WGRegionEvents-1.1.jar \
     -DgroupId=com.mewin -DartifactId=WGRegionEvents -Dversion=1.1
```
