# MenohSharp

C# binding for [Menoh](https://github.com/pfnet-research/menoh/) DNN inference library.

This project is for 64 bit only.

[Nuget](https://www.nuget.org/packages/MenohSharp/)

# Requirements

- [Menoh](https://github.com/pfnet-research/menoh/)

- [Prebuild Binaries(Windows)](https://github.com/pfnet-research/menoh-sharp/releases/download/untagged-fc32366daa771aa93ad1/Prebuild_Win.zip)

To execute an example, please put binaries in ./bin/

## Windows

Visual Studio 2015 or later

## Mac

mono or Visual Studio For Mac

## Linux(Experiment)

mono

# Build

## Windows

Double click retrieve_data.bat or execute below command in root directory .

```
retrieve_data.bat
```

Open MenohSharp.sln and compile with Visual Studio 2015 or later.

## Mac, Linux

Execute below command in root directory.

```
sh retrieve_data.sh
xbuild MenohSharp/MenohSharp.csproj /t:build /p:Configuration=Release /p:Platform=x64
```

# Running VGG16 example

## Windows

Execute ./bin/MenohSharpExample.exe

## Mac, Linux

Execute below command in root directory.

```
xbuild MenohSharp/MenohSharp.csproj /t:build /p:Configuration=Release /p:Platform=x64
cd menoh
mono MenohSharpExample.exe
```

If libgdiplus.dylib is not found on Mac, please execute below command (brew and cask are required)

```
brew cask install mono-mdk
```

 Result is below

```
-22.45651 -34.58567 -10.29389 24.40432 -0.2879904 -7.913781...
top 5  categories are
8 0.9613832  categories aren01514859 hen
7 0.03693673  categories aren01514668 cock
86 0.001228112  categories aren01807496 partridge
82 0.000224892  categories aren01797886 ruffed grouse, partridge, Bonasa umbellus
97 3.720724E-05  categories aren01847000 drake
```

# Licence

Note: `retrieve_data.sh` downloads `data/VGG16.onnx`. `data/VGG16.onnx` is generated by onnx-chainer from pre-trained model which is uploaded
at http://www.robots.ox.ac.uk/%7Evgg/software/very_deep/caffe/VGG_ILSVRC_16_layers.caffemodel

That pre-trained model is released under Creative Commons Attribution License.

The library license is as follows.

- [LICENSE](LICENSE)