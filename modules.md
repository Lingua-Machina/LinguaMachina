Modules are files that contains Lingua Machina code.
When importing values from a module, a path relative to the root of the project is used.
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

A *module* object is instanciated for every loaded module. This object is responsible of import/export.
Code in modules is executed once then the module exports are cached.
