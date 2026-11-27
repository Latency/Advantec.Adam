# Advantech AdamApax Win32

This NuGet package contains the Advantech Adam, Common, Graph and Protocol assemblies and their XML documentation from the Win32 class library. The assemblies target .NET Framework 4.8; consumers should verify compatibility and use the appropriate process architecture for their Advantech installation.

The packaging project targets both `net48` and `net11.0`, but its assembly is not included in the package. The vendor DLLs are packaged only as `net48` assets: the project target does not establish .NET 11 compatibility. A .NET 11 consumer may use NuGet's .NET Framework compatibility fallback and receive warning NU1701; runtime behavior requires validation, and Graph depends on Windows Forms.

Each vendor DLL retains its own assembly identity, version and metadata. The package attribution identifies Advantech, and its copyright range covers the years shown in those DLLs.

The vendor files are not included in this repository. Obtain the Advantech Adam, Common, Graph and Protocol DLLs and their matching XML documentation from an authorized source and place them in `lib` before packing. The vendor assemblies remain subject to Advantech's license terms. Confirm that those terms permit redistribution before publishing the package.

To create a Release package, run `dotnet pack Advantec.csproj -c Release -p:TargetFrameworks=net48` from this directory. NuGet normalizes the version in the filename.
