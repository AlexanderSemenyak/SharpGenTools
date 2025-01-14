origin: https://github.com/SharpGenTools/SharpGenTools

# SharpGenTools

[![Build status](https://github.com/SharpGenTools/SharpGenTools/workflows/Build/badge.svg)](https://github.com/SharpGenTools/SharpGenTools/actions)
[![NuGet](https://img.shields.io/nuget/v/SharpGenTools.Sdk.svg)](https://www.nuget.org/packages/SharpGenTools.Sdk) [![Docs](https://readthedocs.org/projects/sharpgentools/badge/?version=latest)](https://sharpgentools.readthedocs.io/en/latest/) [![codecov](https://codecov.io/gh/SharpGenTools/SharpGenTools/branch/main/graph/badge.svg)](https://codecov.io/gh/SharpGenTools/SharpGenTools) [![CodeFactor](https://www.codefactor.io/repository/github/sharpgentools/sharpgentools/badge)](https://www.codefactor.io/repository/github/sharpgentools/sharpgentools)

Accurate and high performance C++ interop code generator for C#.

## Features

* Accurate, fast code-gen for C++ and COM interfaces from their C++ headers.
* No dependencies on .NET Runtime COM support
* Supports passing code-gen information through MSBuild project and package references
* Pluggable Runtime Library Name and runtime support type names (default library is SharpGen.Runtime)
  * Projects that implement their own SharpGenTools runtime support classes can add mapping rules to ensure that their generated code uses their runtime support library.

## Components in this Repo

* SharpGen
  * The code-gen engine that runs CastXML to parse the C++ and then generates the C# interop code.
  * API for SharpGen SDK plugins, e.g. documentation providers.
* SharpGenTools.Sdk
  * MSBuild tooling to integrate SharpGen directly into projects.
  * Build-time code generation plugin platform.
* SharpGen.Runtime
  * Runtime support classes for code generated by SharpGen.
* SharpGen.Runtime.COM
  * Mapped classes for the core interfaces in the COM and Windows Runtime.

## Requirements

### To Use

* SDK-style (CPS) MSBuild projects
* .NET environment, at least one of the following: 
  * .NET SDK (7 or newer)
  * .NET Core SDK (3.1 or newer)
  * Visual Studio 2019 with desktop .NET workload, .NET Framework 4.7.2 SDK or newer
* Make any mapping files a `SharpGenMapping` item in your `.csproj`.

### To Build

* .NET SDK: 7.0 or newer.
* CMake: 3.0 or newer.
* SDK tests require x64 Windows, VS2022 with x86 and x64 C++ compilers, recent PowerShell version.
