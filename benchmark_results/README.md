# Benchmark Results on M1 Mac

## Library versions:

[fca_unordered](https://github.com/joaquintides/fca_unordered)
f683e9bd099e0d87995df4f0fdb1980f4cda3383

[boost](https://github.com/boostorg/boost): 
ac218462f30cd4bf518afee722b09988a018a404

[abseil](https://github.com/abseil/abseil-cpp): 
4c015dbb49fcfac25899f3ba7da4be665b5f9aab

## Compilers
- Apple Clang 13.0.0
- GCC 11 (Homebrew)

## Compilation Commands
```
{clang++,g++} -std=c++20 -arch arm64 -O3 -DNDEBUG ….cpp -o ….out
```
with `-DHAVE_ABSEIL` or `-DHAVE_ABSEIL -DBENCHMARK_EVERYTHING`

## File Names
`{arm64}_{clang,gcc}_{common,every}_{str,sv,u32,u64}.txt`
- `{common,every}`
  - `common`: compiled with `-DHAVE_ABSEIL`
  - `every`: compiled with `-DHAVE_ABSEIL -DBENCHMARK_EVERYTHING`
- `{str,sv,u32,u64}`
  - `str`: `string.cpp`
  - `sv`: `string_view.cpp`
  - `u32`: `uint32.cpp`
  - `u64`: `uint64.cpp`
