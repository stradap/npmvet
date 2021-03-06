![](./.github/banner.png?raw=true)

NPM Vet is a simple CLI tool to help vet your npm package versions. NPM Vet can be used locally, or as a CI build-step to prevent builds passing with mismatched package versions. To read more about NPM Vet, visit the [Hark website](https://harksys.com/labs/npm-vet-a-simple-cli-tool-for-checking-npm-package-versions).

## Installation

    $ npm install npmvet -g

## Usage

    Usage: npmvet [options]

    Options:

      -h, --help                 output usage information
      -V, --version              output the version number
      -p, --package <package>    package.json file location (Default: .)
      -m, --modules <modules>    node_modules folder location (Default: .)
      -r, --renderer <renderer>  Renderer to use (Default: inlinetable)

## Renderers

Renderers are used to dictate how to output the data NPM Vet collects. The default is `inlinetable`.

### Inline Table

    $ npmvet -r inlinetable

The default renderer, `inlinetable` will print a table inline with your current process. You can use this locally to visualise package differences.

![](./.github/inlinetable.png?raw=true)

### CI

    $ npmvet -r ci

To prevent your CI builds passing with mismatched package versions, use the CI renderer. If any package version mismatches are found, the build will fail:

![](./.github/ci-error.png?raw=true)

Or if there are no mismatching package versions, your build will continue (and hopefully pass!):

![](./.github/ci-success.png?raw=true)

### Blessed

The `blessed` renderer will render a table inside a screen, that has be exited by the user to escape.

    $ npmvet -r blessed

![](./.github/blessed.png?raw=true)

## Contributing

For information regarding contributing to this project, please read the [Contributing](./CONTRIBUTING.md) document.

## License

[MIT License](./LICENSE.md)
