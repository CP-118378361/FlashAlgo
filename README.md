# FlashAlgo

Framework for building Arm "FLM" style flash programming algorithms.


## Development Setup

Skip any step where a compatible tool already exists

1. Install [Python 3.6 or later](https://www.python.org/downloads/) and make sure it's added to path
2. Install [Git](https://git-scm.com/downloads) and make sure it's added to path
3. Install a supported toolchain:
    1. [GNU Arm Embedded](https://developer.arm.com/tools-and-software/open-source-software/developer-tools/gnu-toolchain/gnu-rm)
    2. [Keil MDK-ARM](https://www.keil.com/download/product/)
4. Install GNU Make.

```
$ git clone https://github.com/mbedmicro/FlashAlgo
$ python3 -mvenv venv
$ source venv/bin/activate
$ pip install -r requirements.txt
```

## Develop

### GCC with Make

1. Update tools and generate project files. This should be done everytime you pull new changes

```
$ progen build -t make_gcc_arm
```

Add the project name(s) to the command if you only want to build a limited set of projects. You can list available projects with `progen list -f projects.yaml projects`.

### MDK

```
$ progen generate -t uvision
$ tools\launch_uvision.bat

```
Now open the project file for the desired target in `.\projectfiles\uvision\<target>\`

To change the RAM base address to something other than the default value of 0x20000000, add the argument `--blob_start <hex-ram-address>` in "Projects ❱ Options ❱ User ❱ After Build/Rebuild section of the µVision project.


## Adding a new project

For adding new targets start from template and use these docs...

## Contributions

We welcome contributions! Please see the [contribution guidelines](CONTRIBUTING.md) for detailed requirements.
In order foster a healthy and safe community, all contributors are expected to follow the
[code of conduct](CODE_OF_CONDUCT.md).

To report bugs, please [create an issue](https://github.com/pyocd/FlashAlgo/issues/new) in the GitHub project.


