# MaaXYZ Package Sources

## How to Use

### NuGet

```ps1
dotnet add package Maa.Framework --prerelease -s https://maaxyz.github.io/pkg/nuget/index.json
```

## How to Maintain

### NuGet

```ps1
cd .\nuget

dotnet tool install -g sleet
$ENV:SLEET_FEED_TYPE="local"
$ENV:SLEET_FEED_PATH="$PWD"
$ENV:SLEET_FEED_BASEURI="https://maaxyz.github.io/pkg/nuget/"
```

- Push
```ps1
sleet push ${PACKAGE_PATHS} --force --skip-existing
```

- Delete
```ps1
sleet retention prune --stable 1 --prerelease 1 --release-labels 1

sleet delete --id maa.framework
sleet delete --id maa.framework.binding
sleet delete --id maa.framework.binding
sleet delete --id maa.framework.binding.native
sleet delete --id maa.framework.native
```

- Others
```ps1
sleet stats
sleet validate
sleet recreate
```

## Acknowledgments

- [Sleet](https://github.com/emgarten/Sleet) \
A static nuget feed generator for Azure Storage, AWS S3, and more.
