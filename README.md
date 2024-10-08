# HeadDrops

This fork of HeadDrops is updated to support Minecraft 1.21+. Previous versions of Minecraft (1.8.8 - 1.18.2) are no
longer supported in this version. The plugin alters the player experience by allowing players on the server to drop
their heads when they die.

## Building from Source

To build the project, you will need:

- [Git](https://git-scm.com/)
- [Java 21](https://www.oracle.com/uk/java/technologies/downloads/) or higher
- [Maven](https://maven.apache.org/) (with environment variables set)

1. Clone the repository

   ```bash
   git clone https://github.com/StupidCraft/HeadDrops.git
   ```

2. From the root directory of the cloned source code, run:

   ```bash
   mvn package
   ```

3. Move the generated JAR file (located in /target directory) to your server/plugins directory

4. Start your server

## API

The plugin contains a custom event that you can hook into that allows you alter the default behavior of the plugin from
your own plugin. Below is an example of how you can make all head drops be pumpkins.

```
@EventHandler
public void onHeadDropped(HeadDropEvent event) {
    // Get the head that is supposed to be dropped
    ItemStack originalHead = event.getHeadDrop();

    // Implement your changes... For example, maybe it's Halloween, and you want all head drops to be a pumpkin head
    event.setHeadDrop(new ItemStack(Material.PUMPKIN));
}
```

## License

MIT
