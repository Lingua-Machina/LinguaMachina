# Modules

---

Modules are files that contains Lingua Machina code. When importing values from a module, a path relative to the root of the project is used. A *module* object is instantiated for every loaded module. This object is responsible of import/export. Code in modules is executed once and the module exports are cached.



## Objects import

```
module import: 'core/io/fs/File;
module import: 'core/io/fs/Directory as: 'Dir;
```



## Objects exports

```
Object subclass: 'Hello;
pleaseRename := 1337;

module export: Hello;
module export; pleaseRename as: 'Renamed;
```



## Example

```
<project root>
    |
    + hello
        |
        + world
        |   |
        |   + wow.lm
        |
        + yall.lm
```

```
module import: 'hello/world/wow/MyClass;
module import: 'hello/yall/Nice;
```

