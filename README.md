# Multi-buildpack

Use multiple buildpacks on your app.

## Usage

Scalingo automatically detects an application to be multi-buildpack as long as there is a `.buildpacks` file at its root. For further details on using multiple buildpacks, please refer to [our documentation](https://doc.scalingo.com/platform/deployment/buildpacks/multi).

## Buildpack Sources

Buildpack URLs ending in `.git` are cloned as Git repositories. URLs ending in `.tgz` or `.tar.gz` are downloaded directly as archives.

When an archive is extracted, its top-level directory is stripped so that the buildpack files are placed directly in the buildpack root.

Other URLs are treated as GitHub repository URLs and downloaded as the `master` branch archive. For example:

```
https://github.com/Scalingo/ruby-buildpack
```

downloads:

```
https://github.com/Scalingo/ruby-buildpack/archive/refs/heads/master.tar.gz
```

To download another branch, append `#branch` to the repository URL:

```
https://github.com/Scalingo/ruby-buildpack#main
```

## License

© David Dollar [https://github.com/ddollar](https://github.com/ddollar/heroku-buildpack-multi)

MIT
