# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](http://keepachangelog.com/en/1.0.0/)
and this project adheres to [Semantic Versioning](http://semver.org/spec/v2.0.0.html).

## [Unreleased]

Nothing.

## [0.3.0] - 2018-03-13

### Added
- Libraries are automatically detected on Windows now as well
- C++ rules allow specifying `linkflags`
- Support for MSVC 2017
- Experimental rules for native Android apps
- New `timeout` parameter for `core.call()`
- Mechanism to prevent accidental deletes by using a wrong build directory
- Loading scripts will now inject a `__file__` variable pointing to the script
- Automatic regeneration has been added to `examples/cpp/clion.py`
- Warning when removing undeclared files in the build directory
- Add WIP (very basic for now) rules for external projects / build systems
- Build can now be stopped gracefully (Ctrl+C)
- Added `-f` / `--fastfail` flag to immediately exit after first failed task
- Renamed `core.source()` to `core.resolve()`

### Changed
- Using `cook --targets` will now list paths relative to the build directory
- Includes in system directories will now be tracked too
- Disabled restriction of output paths having to be in the build directory
- `core.call` will now use all environment variables as a default
- Using `Ctrl+C` will now save process and let the system shutdown properly

### Fixed
- The task-failed handler was not properly protected against exceptions
- Warning retrieval was broken


## [0.2.0] - 2017-08-17
### Added
- Decorator to `core.cache()` function results
- New generic rule `misc.run()`
- Basic option enumeration by using `cook --options`
- C++ toolchains are now public (`cpp.GNU` and `cpp.MSVC`)
- C++ compile time definitions are now properly translated by type
- Check if all options were consumed

### Changed
- Detect now all MSVC versions from 7.0 to 14.0 (2015)
- Globbing with `core.glob()` will return only files for now
- Exceptions and tracebacks are now correctly displayed

### Fixed
- `core.glob()` was not recursive under some circumstances
- Output paths were not properly verified
- `cpp.object` was using wrong paths if name was specified
- Messages regarding failed tasks could interleave


## 0.1.0 - 2017-07-27

Initial version.

[Unreleased]: https://github.com/jachris/cook/compare/v0.3.0...HEAD
[0.3.0]: https://github.com/jachris/cook/compare/v0.2.0...v0.3.0
[0.2.0]: https://github.com/jachris/cook/compare/v0.1.0...v0.2.0
