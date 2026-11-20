# libassert: the cscosine fork

libassert, as built and released by [third_party_base_libs](https://github.com/cscosine/third_party_base_libs) for the
cscosine projects: the upstream release plus a few commits of ours on top. This folder is ours; the rest of the
repository is upstream.

| | |
|---|---|
| Upstream | <https://github.com/jeremy-rifkin/libassert> |
| Base | upstream tag `v2.2.1` (also in this repository) |
| Our changes | `git log v2.2.1..dev` |
| Our releases | tags `v2.2.1-cs.<n>`, see [CHANGELOG.md](CHANGELOG.md) |
| License | upstream's (MIT) |

## Our changes

| Commit | Files | Why |
|---|---|---|
| csCMake presets: the fork built with the csCMake presets on every platform | `CMakePresets.json`, `csCMakeProjectSetup.json` | Built with the csCMake presets; macOS 13.3 for the floating-point `std::to_chars` |
| Debug libraries with the d postfix | `CMakeLists.txt` | Debug and Release in one install prefix, as the other libraries |
| cpptrace from find_package (LIBASSERT_USE_EXTERNAL_CPPTRACE ON by default) | `cmake/OptionVariables.cmake` | One cpptrace for the consumers of both |
| clang, C++17 with -Wpedantic: no -Wgnu-zero-variadic-macro-arguments from an assertion without message | `include/libassert/assert-macros.hpp` | No warning in consumers' code with clang + `-Wpedantic` (candidate for upstream) |
| cscosine/: where the fork comes from | `cscosine/README.md`, `CHANGELOG.md` | Where the fork comes from, what we change, why |

Upstream's `.github/` stays as it is: GitHub Actions is disabled on this repository.

## Syncing with a new upstream release

Fetch the new upstream tag (`git fetch https://github.com/jeremy-rifkin/libassert.git refs/tags/<new>:refs/tags/<new>`), rebase our commits on
it (`git rebase --onto <new> v2.2.1 dev`), drop those upstream has absorbed, build through third_party_base_libs,
then tag `v<new without v>-cs.1`.
