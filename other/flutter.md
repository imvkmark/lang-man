# man - flutter(9)

Manage your Flutter app development.

Common commands:

```
flutter <command> [arguments]
```

```sh
# Create a new Flutter project in the specified directory.
flutter create <output directory>
    
# Run your Flutter application on an attached device or in an emulator.
flutter run [options]
```

## Usage: 

**Global options:**

`-h, --help`                  
Print this usage information.
`-v, --verbose`               
Noisy logging, including all shell commands executed.
If used with `--help`, shows hidden options.

`-d, --device-id`
Target device id or name (prefixes allowed).
`--version`
Reports the version of this tool.
`--suppress-analytics`
Suppress analytics reporting when this command runs.
`--bug-report`
Captures a bug report file to submit to the Flutter team.
Contains local paths, device identifiers, and log snippets.

`--packages`              
Path to your ".packages" file.(required, since the current directory does not contain a ".packages" file)

**Available commands:**

`analyze`
Analyze the project's Dart code.

`assemble`
Assemble and build flutter resources.

`attach`
Attach to a running application.

`bash-completion`
Output command line shell completion setup scripts.

`build`
Flutter build commands.

`channel`
List or switch flutter channels.

`clean`
Delete the build/ and .dart_tool/ directories.

`config`
Configure Flutter settings.

`create`
Create a new Flutter project.

`devices`
List all connected devices.

`doctor`
Show information about the installed tooling.

`drive`
Runs Flutter Driver tests for the current project.

`emulators`
List, launch and create emulators.

`format`
Format one or more dart files.

`help`
Display help information for flutter.

`install`
Install a Flutter app on an attached device.

`logs`
Show log output for running Flutter apps.

`make-host-app-editable`
Moves host apps from generated directories to non-generated directories so that they can be edited by developers.

`precache`
Populates the Flutter tool's cache of binary artifacts.

`pub`
Commands for managing Flutter packages.

`run`
Run your Flutter app on an attached device.

`screenshot`
Take a screenshot from a connected device.

`test`
Run Flutter unit tests for the current project.

`upgrade`
Upgrade your copy of Flutter.

`version`
List or switch flutter versions.


Run "flutter help <command>" for more information about a command.
Run "flutter help -v" for verbose help output, including less commonly used options.