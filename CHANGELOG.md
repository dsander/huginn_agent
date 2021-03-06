# Change Log

All notable changes to this project will be documented in this file.

## Unreleased

### Added

### Changed

## [0.5.0] - 2017-02-03

### Added
- Generate Agent gem code coverage report with `COVERAGE=true rake spec` and allow to report to coveralls (@stesie)

### Fixed
- Generator: Do not include `spec/huginn` files in build gem (@stesie)

  The `gemspec` of existing gems needs to be updated manually:
  ```patch
  -  spec.test_files    = Dir['spec/**/*.rb']
  +  spec.test_files    = Dir['spec/**/*.rb'].reject { |f| f[%r{^spec/huginn}] }
  ```

- Generator: Do not run Agent specs on ruby `2.1` (@stesie)

  The `.travis.yml` of existing gems needs to be updated manually:
  ```patch
  rvm:
  -- 2.1
  -- 2.2
  +- 2.2.2
   - 2.3.0
  ```

## [0.4.3] - 2016-09-07

### Fixed
- Exclude Huginn spec files when running Agent gem specs (@dsander)

## [0.4.2] - 2016-08-10

### Changed
- Run all Agent spec files in the spec directory recursively (@dsander)


## [0.4.1] - 2016-06-23

### Changed
- Generator: Do not lock the `huginn_agent` gem version (@dsander)

  The `gemspec` of existing gems needs to be updated manually:
  ```patch
  -  spec.add_runtime_dependency "huginn_agent", '~> 0.2'
  +  spec.add_runtime_dependency "huginn_agent"
  ```

## [0.4.0] - 2016-06-20

- First official and working release


[Unreleased]: https://github.com/cantino/huginn_agent/compare/v0.5.0...HEAD
[0.5.0]: https://github.com/cantino/huginn_agent/compare/v0.4.3...v0.5.0
[0.4.3]: https://github.com/cantino/huginn_agent/compare/v0.4.2...v0.4.3
[0.4.2]: https://github.com/cantino/huginn_agent/compare/v0.4.1...v0.4.2
[0.4.1]: https://github.com/cantino/huginn_agent/compare/v0.4.0...v0.4.1
[0.4.0]: https://github.com/cantino/huginn_agent/compare/f6e307e2ec1679367ecc43ab265b8f68d6fe12f2...v0.4.0
