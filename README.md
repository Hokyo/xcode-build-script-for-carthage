# XCode Build Script for Carthage

If you use Carthage as the library dependency manager, you must manually configure the framework path to Build phases and Build settings in XCode after run 'carthage update'. However, using this script after run 'carthage update' eliminates the need to manually configure the framework path.

After 'carthage update', this script add a run script for Carthage, sets up the framework dependency to Xcode Build phases and add framework search paths to XCode Build Settings


## Quickstart

#### This script uses [Xcodeproj](https://github.com/CocoaPods/Xcodeproj). Install it by performing the following command:
```console
$ [sudo] gem install xcodeproj
```

#### 1. To use the script, open the ruby file (Source/carthage_build_setup.rb)
> Enter the target of your project in @scriptTargets you want to apply the script to.
```ruby
# Constants
@scriptTargets = []
```
> Enter the path to your project.
```ruby
# Constants
CARTHAGE_FRAMEWORK_PATH = "YOUR_CARTHAGE_FOLDER_PATH/Carthage/Build/iOS"

# Variables
@project = Xcodeproj::Project.open"YOUR_PROJECT_PATH/YOUR_PROJECT_NAME.xcodeproj"
```

#### 2. Move the script file to your project path.

#### 3. Run
```console
$ carthage update
$ ruby carthage_build_setup.rb
```

#### 4. Press check, your project Build Phases and Framework Search Paths in Build Settings


## Example
### Building Project

1. Install Carthage libraries.
    ```console
    $ carthage update
    $ cd Scripts
    $ ruby carthage_build_phase_setup.rb
    ```
      or
    ```console
    $ cd Scripts
    $ sh carthage_update.sh
    ```

2. Open **`CarthageScriptExample.xcodeproj`** file.
3. Press <kbd>⌘</kbd> + <kbd>B</kbd> to build the project.
4. Press check, the build is succeeded
5. Press check, your project Build Phases and Framework Search Paths in Build Settings
![script_completed](https://user-images.githubusercontent.com/15151687/41157050-48e473c8-6b5f-11e8-851c-6dcb725aaf0f.png)


## LICENSE

These works are available under the MIT license. See the [LICENSE][license] file
for more info.

[ruby]: http://www.ruby-lang.org/en/
[license]: LICENSE
