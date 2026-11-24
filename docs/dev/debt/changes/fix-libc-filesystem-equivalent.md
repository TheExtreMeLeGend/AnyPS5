# libSceLibcInternal

## change [_ZNSt10filesystem11_EquivalentEPKcS1_]

- [_ZNSt10filesystem11_EquivalentEPKcS1_](../../../core/libs/prx/libSceLibcInternal/Filesystem.cpp) (libSceLibcInternal, NID `XD9FmX1mavU`) - the mangled PS5 name gives two narrow paths. The integer return convention follows [Dinkumware](https://github.com/microsoft/STL/blob/219514876ea86491de191ceaa88632616bbc0f19/stl/src/filesys.cpp#L327-L382): -1 if neither path can be inspected, 0 if only one can be inspected or the identities differ, and 1 if the identities match. The guest implementation follows links with `sceKernelStat` and compares its 32-bit device and inode fields. Host identities that collide in those fields cannot be distinguished. The return type and behavior are unverified on PS5.
