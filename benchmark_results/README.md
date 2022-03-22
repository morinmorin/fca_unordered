# Benchmark Results on Apple M1 Pro

## Library versions:
- fca_unordered: https://github.com/joaquintides/fca_unordered/commit/228d40521a1aa946e4891c8b69933d1471e8b969
- boost: https://github.com/boostorg/boost/commit/ac218462f30cd4bf518afee722b09988a018a404
- abseil: https://github.com/abseil/abseil-cpp/commit/6c8dab80c06820f475ce0a1fe873b8022cb274f6

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
