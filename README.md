# job-nuget-library-release
An action that sets up the `dotnet` environment to , then runs the [action-nuget-push](https://github.com/EasyDesk/action-nuget-push) action to deploy NuGet packages.

## Usage
This action pushes all files with the `.nupkg` extension to the specified NuGet source, using the specified `dotnet` version.

### Usage example
```yaml
    steps:
      - uses: EasyDesk/job-nuget-library-release@v1
        with:
          # (Required) The dotnet version version to be used.
          dotnet-version: '5.x'

          # (Required) The API key used to authenticate the upload of the package.
          # Can be generated via the NuGet portal.
          nuget-api-key: '<your-api-key>'

          # (Optional) The URL to the NuGet source where packages will be uploaded.
          # If not specified, defaults to nuget.org (https://api.nuget.org/v3/index.json).
          nuget-url: '<your-nuget-url>'

          # (Optional) A directory where all your .nupkg files are located.
          # If not specified, defaults to the current directory.
          publish-dir: '<your-publish-directory>'
```