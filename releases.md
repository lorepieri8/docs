# Ignition Releases

This page details the set of past and planned releases.

## What is a Release?

A release of Ignition consists of a set of versioned [Ignition Libraries](/libs). Each library follows [semantic versioning](https://semver.org), and the major version of a library is guaranteed not to change with an Ignition release. This essentially means you can develop code against a release of Ignition without the worry of breaking changes being made upstream.

### Naming Scheme

An Ignition release follows the form "Ignition Codename", for example Ignition Acropolis. The codename is alphabetically increasing, and chosen to fall loosely within the architectural domain.

## Release List

| Name                                                     | Date      | EOL date  | Notes |
|----------------------------------------------------------|-----------|-----------|-------|
| [Acropolis](https://ignitionrobotics.org/docs/acropolis) | Feb, 2019 | Sep, 2019 | EOL   |
| [Blueprint](https://ignitionrobotics.org/docs/blueprint) | May, 2019 | Dec, 2020 | EOL   |
| [Citadel](https://ignitionrobotics.org/docs/citadel)     | Dec, 2019 | Dec, 2024 | LTS   |
| [Dome](https://ignitionrobotics.org/docs/dome)           | Sep, 2020 | Dec, 2021 | EOL   |
| [Edifice](https://ignitionrobotics.org/docs/edifice)     | Mar, 2021 | Mar, 2022 |       |
| [Fortress](https://ignitionrobotics.org/docs/fortress)   | Sep, 2021 | Sep, 2026 | LTS   |
| [Garden](https://ignitionrobotics.org/docs/garden)       | Sep, 2022 | Sep, 2024 |       |
| Ignition-H                                               | Sep, 2023 | Sep, 2028 | LTS   |
| Ignition-I                                               | Sep, 2024 | Sep, 2026 |       |

## Library Versions

Ignition adheres to [semantic versioning](https://semver.org), with the
addition that ABI is considered part of the public interface. In summary:

* **Major** version increased when incompatible ABI/API changes are made.
* **Minor** version increased when functionality has been added in a
  backwards-compatible manner, but it may not be forward-compatible. That is,
  code compiled against minor `N` will work with minor `N+1`, but code compiled
  against minor `N+1` may not work with minor `N`.
* **Patch** version increased when backwards-compatible bug fixes are released.
* **Pre-release** version used before making stable releases, using the `~`
  separator.

### Deprecation strategy

Where possible, a tick-tock deprecation strategy is used during major version
increments. Deprecated code produces compile-time or runtime warnings (tick).
These warnings serve as notification to users that their code should be upgraded.
The next major release removes the deprecated functionality (tock).

Example of function `foo` deprecated and replaced by function `bar`:

Version     | API
----------- | ---
Ign-(N)     | void foo();
Ign-(N+1)   | void foo() IGN_DEPRECATED(N+1); <br> void bar();
Ign-(N+2)   | void bar();

### Support lifecycle

Check out [this table](https://github.com/ignitionrobotics/docs/blob/master/tools/versions.md)
for a list of release and EOL dates for all versions of all libraries.

### Supported platforms

Platforms are defined as a combination of operating system and architecture.
For example, "Ubuntu Focal on amd64".

Each release is targeted at a specific set of platforms. A support level applies
to an entire Ignition release, including all library versions within it. The
supported platforms for each release are listed on their home pages (i.e.
[Fortress](https://ignitionrobotics.org/docs/fortress)).

In general, there are three categories of support for a platform:

* **Official support**: Officially supported platforms are regularly tested on
  continuous integration and released as binary packages. Errors or bugs
  discovered in these platforms are prioritized for correction by the
  development team. Significant errors discovered in these platforms can impact
  release dates and we strive to resolve all known high priority errors in
  officially supported platforms prior to new version releases.
* **Best-effort support**: Platforms supported at best-effort may be regularly
  tested on continuous integration and / or released as binary packages. Errors
  may be present in released versions for these platforms. Known errors in
  best-effort platforms will be addressed subject to resource availability on a
  best-effort basis and may or may not be corrected prior to new releases.
* **No effort to support**: All platforms not included under official or
  best-effort support are considered not supported. If a release is functional
  in a platform that isn't supported at a point in time, there are no guarantees
  that it will remain so in the future. Pull requests addressing issues on these
  platforms may be considered if they don't break any supported platforms and
  reviewed as time allows.

If you or your company are interested in directly supporting, or
sponsoring the support of other platforms, please contact
`info@openrobotics.org`.

