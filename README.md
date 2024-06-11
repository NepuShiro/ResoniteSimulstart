Simulstart
==========

A [ResoniteModLoader](https://github.com/resonite-modding-group/ResoniteModLoader) mod for [Resonite](https://resonite.com/) that makes it possible to launch other processes together with Resonite.  
Processes can be launched with (a request for) administrator privileges and can automatically be closed with the game as well.

## Installation
1. Install [ResoniteModLoader](https://github.com/resonite-modding-group/ResoniteModLoader).
2. Place [Simulstart.dll](https://github.com/Banane9/ResoniteSimulstart/releases/latest/download/Simulstart.dll) into your `rml_mods` folder. This folder should be at `C:\Program Files (x86)\Steam\steamapps\common\Resonite\rml_mods` for a default install. You can create it if it's missing, or if you launch the game once with ResoniteModLoader installed it will create the folder for you.
3. Start the game. If you want to verify that the mod is working you can check your Resonite logs.

## Usage

Since ResoniteModSettings can't handle custom types, this mod requires editing its settings file to add or remove processes.

It should look as follows:
```JSON
{
    "version":"1.0.0",
    "values":
    {
        "ProcessesToLaunch":
        [
            {
                "Administrator":true,
                "Arguments":"-extra LaunchArguments",
                "KeepOpen":true,
                "Path":"C:\\Path\\To\\AdministratorExecutable.exe",
                "WorkingDirectory": "C:\\Path\\To\\WorkingDirectory"
            },
            {
                "Restart": true,
                "Path":"C:\\Path\\To\\SimpleExecutable.exe"
            }
        ]
    }
}
```


| Field  | Usage |
| :---: | :--- |
| `Administrator` | Launch process with administrator privileges if `true`. Default: `false` |
| `Arguments` | Launch process with extra parameters. Default: none |
| `KeepOpen` | Leave process running when Resonite is getting shut down. Default: `false` |
| `Path` | The path of the executable file to launch. Required value. |
| `Restart` | Restart process if it exits while Resonite is still running. Default: `false` |
| `WorkingDirectory` | The directory to execute the file in. Default: The executable's directory. |