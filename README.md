## ts-loader-symlink-reproduction

This is a reproduction for an issue with ts-loader (https://github.com/TypeStrong/ts-loader/issues/1344).

When a package in `node_modules` is a symlink, building with ts-loader will fail with an error complaining that files in the package are outside `rootDir`. Both webpack without ts-loader and tsc compile the project just fine.

Steps to reproduce

```
cd main
yarn install

yarn run build-with-tsc # This works just fine and produces index.js in dist

yarn run build-without-ts-loader  # This works also fine and produces main.js in dist

yarn run build-with-ts-loader # This fails with TS6059
```
