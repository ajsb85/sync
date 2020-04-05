# protocol-sync

Sync [Protocol CSS](https://github.com/ajsb85/protocol-sync) SCSS files installed with npm out of `node_modules`.

If you use Protocol CSS with Jekyll on GitHub Pages, this is for you:

```sh
npx -p @mozilla-protocol/core protocol-sync
```

And that's it! All of the Protocol CSS source files will be copied to your `_sass` directory so that you can use them without adding `node_modules` to your Sass include paths. Then, you can add these files to git instead of `node_modules`, and your site will build on Pages! :sparkles:


## Installation

If you plan on updating Protocol CSS regularly, you should add it as a dev dependency with:

```sh
npm i -D @ajsb85/protocol-sync
```

Then, whenever you update your `protocol` or `protocol-*` dependencies, you can run it with:

```sh
npx protocol-sync
```


## Usage

The `protocol-sync` command line script works like this:

```
protocol-sync [options] [<output directory>]

Options:
  --help, -h      Show help                                            [boolean]
  --version       Show version number                                  [boolean]
  --from                                      [string] [default: "node_modules"]
  --packages, -p                               [string] [default: "@mozilla{,-*}"]
  --files, -f                                             [default: "**/*.scss"]
  --dry-run, -n                                                        [boolean]
```

For instance:

* `protocol-sync foo` will copy all of the Protocol CSS source files from
  `node_modules` to a directory named `foo` in your current working directory.
* `protocol-sync --from ../node_modules src/_sass` will tell it to look for your
  npm modules in `../node_modules` and copy them to `src/_sass`.
* `protocol-sync --files '**/*.md'` will copy only Markdown (documentation) files
  rather than the SCSS sources.
* `protocol-sync --dry-run` (or `protocol-sync -n`) will print the copy operations
  so you can confirm what will be copied before actually doing it.


## License

[MIT](./LICENSE) &copy; [ajsb85](https://ajsb85.com/)
