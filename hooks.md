# Resolve Plugin Hooks

List of hooks assumed from [here](https://github.com/webpack/enhanced-resolve/blob/635c2c7e33910bb89845bbeb8ef2c4eda36527f2/lib/ResolverFactory.js#L152-L167)

Can also access derived hooks **before** or **after** below hooks (e.g. `before-existing-directory`)

Each internal plugin gets passed in `source` and `target` types on instantiation. `source` means the resolve hook that the plugin will execute against, in sequence. For a plugin that can satisfy the request, it will call the resolver's `doResolve` method w/ the `target` type ([source](https://github.com/webpack/webpack.js.org/issues/1458#issuecomment-330445790)).

## resolve

Starts resolving process

## parsedResolve

## describedResolve

## rawModule

## module

## relative

## describedRelative

## directory

## existingDirectory

## undescribedRawFile

## rawFile

## file

## existingFile

## resolved
