# Il2CppDumperGui-Critical-Ops

Fixed IL2CPP dumper for Critical Ops.

**TL;DR:** The fix was not a hidden exported function. The shipped metadata uses a compact custom header that the stock dumper rejected. IDA showed how the runtime reads that layout. A small metadata adapter reuses the compact readers already in the project, and a separate dummy-assembly hierarchy fix resolves missing nested definitions.

Tested on Android, Critical Ops `1.80.0.f3391`, arm64.

Newer builds may break the layout again. If they do, I'll fix it.

**Requirements**

- .NET 7.0 runtime

**Usage**

1. Run `Il2CppDumper.exe`.
2. Select the IL2CPP executable and `global-metadata.dat`.
3. Enter the prompts as asked.
4. Output files are written to the current working directory.

**Credits**

- Perfare — original Il2CppDumper
- Base: `https://github.com/dsgaming-mrd/Il2CppDumper-GUI-Fixed`
