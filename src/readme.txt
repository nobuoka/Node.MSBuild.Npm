Node.MSBuild.Npm
====================

## This NuGet package provides following MSBuild targets.

* `SetupNpm`
    * It downloads npm zip file, extracts it, and move npm directory to specified location.
    * The default location is `%USERPROFILE%/.node-msbuild/npm-{version}`.
    * Changing the version of Node.js to be installed, set the version as the value of MSBuild property `NpmVersion`.
      For example: `<NpmVersion>3.5.2</NpmVersion>`.
    * This target is included in `BuildDependsOn` property.
* `NpmInstall`
    * It executes `npm install`.
    * This target is included in `BuildDependsOn` property.
* `NpmBuild`
    * It executes `npm run-script build` if `build` script is defined in your `package.json`.
    * This target is included in `CompileDependsOn` property.
      
## Usage
      
* Executing `npm` command, use `Exec` task with `NpmCommand` property:
    * For example: `<Exec Command="$(NpmCommand) run-script xxx" />`.
