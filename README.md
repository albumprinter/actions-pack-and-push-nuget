# Pack And Push NuGet Package To NuGet Server

A GitHub Action to pack and push a [nuget package](https://docs.microsoft.com/en-us/dotnet/core/tools/dotnet-nuget-push).

You could use [albumprinter/actions-get-git-version](https://github.com/albumprinter/actions-get-git-version) to get the semver using git log.

## Usage

```yaml
  - uses: albumprinter/actions-pack-and-push-nuget@v1
    with:
        package: YOUR_PACKAGE_NAME
        description: YOUR_PACKAGE_DESCRIPTION
        version: YOUR_PACKAGE_VERSION or ${{ steps.git-version.outputs.version }}
        paths: dist deploy.sh
        server: ${{ secrets.ARTIFACTORY_DEPLOY_RELEASE_URL }}
        username: ${{ secrets.ARTIFACTORY_USERNAME }}
        password: ${{ secrets.ARTIFACTORY_USER_PASSWORD }}
```
