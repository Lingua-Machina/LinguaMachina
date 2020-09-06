# Global variables
```
LinguaMachina globalVars |> setVar: 'Hello to: 1337;

Hello println # Prints 1337 #
```

# Importing objects

```
module importAll: 'core/io/fs as: 'fs;
module importAll: 'core/io/fs;
module import: 'core/io/fs/File;
module import: 'core/io/fs/Directory as: 'Dir;
```
