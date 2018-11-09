# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](http://keepachangelog.com/en/1.0.0/)
and this project adheres to [Semantic Versioning](http://semver.org/spec/v2.0.0.html).

## [Unreleased]
- Fix Issue #67
  - Dependency on [Swashbuckle.AspNetCore](https://github.com/domaindrivendev/Swashbuckle.AspNetCore) 4.0.1 instead of 3.0.0 (netstandard2.0 and net461 only, netstandard1.6 remains on 3.0.0)
  
## [4.3.1] - 2018-10-08
### Added
- Fix Issue #63
  - Add an optional true/false value to the AddHeaderOperationFilter to determine whether the header
    is required or not.

## [4.3.0] - 2018-09-14
### Changed
- Fix Issue #60
  - No longer support .NET Framework 4.5.1 because it doesn't work with Scrutor (because Scrutor is unsigned)
  - Support .NET Framework 4.6.1
  - Support .NET Standard 2.0 (still support 1.6 too)

### Deprecated
- Mark DescriptionOperationFilter as obsolete, because you can accomplish the same thing with summary tags

## [4.2.0] - 2018-08-15
### Changed
- It is no longer necessary to specify a ProducesResponseType or SwaggerResponse attribute in order to get
response examples, so long as it is obvious what Type your action method returns.

## [4.1.0] - 2018-08-06
### Added
- Add generic version of SecurityRequirementsOperationFilter and AppendAuthorizeToSummaryOperationFilter so that
they can be used with other attributes. Reason: a client had implemented their own `TypeFilterAttribute`
which did Authorization but wasn't an `AuthorizeAttribute`

## [4.0.3] - 2018-08-03
### Fixed
- Issue #54 where child objects weren't having their descriptions set if parent property was missing `[Description]`

## [4.0.2] - 2018-07-26
### Fixed
- Issue #54 where arrays of child objects weren't having their description set

## [4.0.1] - 2018-07-24
### Fixed
- Fix bug where generic types weren't being automatically annotated

## [4.0.0] - 2018-07-23
### Added
- Automatic annotation of request and response examples
- Dependency on [Scrutor](https://github.com/khellang/Scrutor) 2.2.2
### Changed
- How ExamplesOperationFilter is installed - see Installation section of the Readme

## [3.1.0] - 2018-07-21
### Added
- SecurityRequirementsOperationFilter to correctly set bearer token stuff when using `[Authorize]`

## [3.0.4] - 2018-07-18
### Fixed
- Fix bug with DescriptionOperationFilter where Description not set if using a DefaultContractResolver

## [3.0.3] - 2018-07-17
### Fixed
- Fix where Examples doesn't work on ASP.NET Core 2.0

## [3.0.2] - 2018-07-15
### Fixed
- Port of bug #36 from Swashbuckle.Examples

## [3.0.1] - 2018-07-15
### Changed
- Rename from Swashbuckle.AspNetCore.Examples
- Dependency on [Swashbuckle.AspNetCore](https://github.com/domaindrivendev/Swashbuckle.AspNetCore) 3.0 instead of 1.0