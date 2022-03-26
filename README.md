# Rift Loader
Rift is a lightweight modding API, library, and mod loader for Minecraft 1.13 and beyond. The main objective of Rift is to make a more modular and lightweight modding API for Minecraft.

This fork contains the port of the loader part of Rift to the modern Minecraft versions(1.13 and beyond). For Minecraft 1.13 see [**here**](https://github.com/DimensionalDevelopment/Rift).

### Using the Minecraft Launcher
Currently, Rift does not have its own installer (The previous one is deleted). However, you can edit a profile by yourself.

Here is an example:
```json
{
  "inheritsFrom": "1.18.2",
  "id": "Rift-1.18.2-2.0.0-20220326-1727",
  "jar": "1.18.2",
  "time": "2022-02-14T19:22:32+0800",
  "type": "release",
  "arguments": {
    "game": [
      "--tweakClass",
      "org.dimdev.riftloader.launch.RiftLoaderClientTweaker"
    ]
  },
  "mainClass": "net.minecraft.launchwrapper.Launch",
  "libraries": [
    {
      "name": "org.spongepowered:mixin:0.8.5",
      "url": "https://repo.spongepowered.org/repository/maven-public/"
    },
    {
      "name": "org.ow2.asm:asm:9.2",
      "url": "https://repo1.maven.org/maven2/"
    },
    {
      "name": "org.ow2.asm:asm-tree:9.2",
      "url": "https://repo1.maven.org/maven2/"
    },
    {
      "name": "org.ow2.asm:asm-commons:9.2",
      "url": "https://repo1.maven.org/maven2/"
    },
    {
      "name": "org.ow2.asm:asm-util:9.2",
      "url": "https://repo1.maven.org/maven2/"
    },
    {
      "name": "org.ow2.asm:asm-analysis:9.2",
      "url": "https://repo1.maven.org/maven2/"
    },
    {
      "name": "cn.enaium:launchwrapper:1.3.0",
      "url": "https://maven.enaium.cn/"
    },
    {
      "name": "org.dimdev:RiftLoader:2.0.0-20220326-1704",
      "url": "https://raw.githubusercontent.com/CliffhangerMC/mvn-repo/main/"
    }
  ]
}
```

### Using MultiMC
Modified original documentation from the [Rift Wiki](https://github.com/DimensionalDevelopment/Rift/wiki/Installing-Rift-in-a-MultiMC-instance#alternate-method)

1. Make a new instance in MultiMC with with the wanted version of Minecraft—in our case, Minecraft 1.18.2
1. Click `Edit Instance`—it should open the `Version` page of the instance.
1. Click `Add Empty`.
1. Set uid to `org.dimdev.RiftLoader` and name to `RiftLoader`.
1. Select the newly created component and click `Edit`—this should open the file in a text editor.
1. Edit the JSON to look like the example below, then save the file.
1. Launch the instance from MultiMC.

If the example doesn't fit the Rift Loader version exactly, change the version. For example, replace all occurrences of `2.0.0-20220326-1524` with `2.0.0-20220326-1727`.

You can use the version page to check the file for errors—obvious mistakes will show up in the `Version` page as soon as you click the `Refresh` button.

If the JSON file doesn't open in a text editor, make sure your operating system is set up to open `.json` files in one first.

#### Example MultiMC Json

```json
{
    "+tweakers": [
        "org.dimdev.riftloader.launch.RiftLoaderClientTweaker"
    ],
    "formatVersion": 1,
    "+libraries": [
        {
            "name": "org.dimdev:RiftLoader:2.0.0-20220326-1727",
            "url": "https://raw.githubusercontent.com/CliffhangerMC/mvn-repo/main/"
        },
        {
            "name": "org.spongepowered:mixin:0.8.5",
            "url": "https://repo.spongepowered.org/repository/maven-public/"
        },
        {
            "name": "org.ow2.asm:asm:9.2",
            "url": "https://repo1.maven.org/maven2/"
        },
        {
            "name": "org.ow2.asm:asm-tree:9.2",
            "url": "https://repo1.maven.org/maven2/"
        },
        {
            "name": "org.ow2.asm:asm-commons:9.2",
            "url": "https://repo1.maven.org/maven2/"
        },
        {
            "name": "org.ow2.asm:asm-util:9.2",
            "url": "https://repo1.maven.org/maven2/"
        },
        {
            "name": "org.ow2.asm:asm-analysis:9.2",
            "url": "https://repo1.maven.org/maven2/"
        },
        {
            "name": "cn.enaium:launchwrapper:1.3.0",
            "url": "https://maven.enaium.cn/"
        }
    ],
    "mainClass": "net.minecraft.launchwrapper.Launch",
    "name": "RiftLoader",
    "releaseTime": "2022-02-14T19:22:32+0800",
    "requires": [
        {
            "equals": "1.18.2",
            "uid": "net.minecraft"
        }
    ],
    "uid": "org.dimdev.RiftLoader",
    "version": "2.0.0-20220326-1727"
}
```
