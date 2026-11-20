# Changelog of the cscosine fork of libassert

## v2.2.1-cs.2 (to tag once third_party_base_libs has built it)

- Our changes as a clean stack on upstream `v2.2.1`; the build is the same as cs.1.
- Upstream's `.github/` and `.gitignore` back as they are (Actions disabled on the repository instead).
- `cscosine/README.md`, this file.

## v2.2.1-cs.1

- Upstream 2.2.1, csCMake presets; Debug libraries with the d postfix; cpptrace from find_package (LIBASSERT_USE_EXTERNAL_CPPTRACE ON by default); clang, C++17 with -Wpedantic: no -Wgnu-zero-variadic-macro-arguments from an assertion without message. The commit third_party_base_libs `v0.1.0-rc8` was built from (and the
  history of the fork before the clean stack).
