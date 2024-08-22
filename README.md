# luals-check-action

A GitHub Action to run LuaLS checks with the [vscode-wow-api](https://github.com/Ketho/vscode-wow-api) library.

Based on [LuaLS-Config](https://github.com/DeadlyBossMods/LuaLS-Config/tree/main) by DeadlyBossMods.

## Usage

```yaml
- name: Run LuaLS check
  uses: Krealle/luals-check-action@v1
  with:
    # Extra arguments to pass to LuaLS
    # See https://luals.github.io/wiki/usage/#arguments
    extra-args:

    # Check level to use
    # See https://luals.github.io/wiki/usage/#--checklevel
    # Defaults to Warning
    checklevel:

    # The relative path to the Lua configuration file used by LuaLS
    # Defaults to `.luarc.json` in the repository root if not specified
    config-path:

    # The relative path to the directory you want LuaLS to check within your repository
    # Use this option to limit the check to a specific directory or folder
    # Defaults to the repository root if not specified
    check-dir:
```

## Examples

### Custom config file

```yaml
- name: Run LuaLS check
  uses: Krealle/luals-check-action@v1
  with:
    config-path: .vscode/settings.json
```

### Custom check directory

```yaml
- name: Run LuaLS check
  uses: Krealle/luals-check-action@v1
  with:
    check-dir: /SomeFolder
```

### Error check level

```yaml
- name: Run LuaLS check
  uses: Krealle/luals-check-action@v1
  with:
    checklevel: Error
```
