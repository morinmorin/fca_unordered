# Benchmark Results on Apple M1 Pro

## Library versions:
- joaquintides/fca_unordered@f683e9bd099e0d87995df4f0fdb1980f4cda3383
- boostorg/boost@ac218462f30cd4bf518afee722b09988a018a404
- abseil/abseil-cpp@4c015dbb49fcfac25899f3ba7da4be665b5f9aab

## Compilers
- Apple Clang 13.0.0
- GCC 11.2 (Homebrew)

## CPU Info
Apple M1 Pro
- 8 performance cores (3.2 GHz) and 2 efficiency cores (2.0 GHz)
- No turbo boost

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
