# Resolve Plugin Hooks

List of hooks assumed from [here](https://github.com/webpack/enhanced-resolve/blob/635c2c7e33910bb89845bbeb8ef2c4eda36527f2/lib/ResolverFactory.js#L152-L167)

Can also access derived hooks **before** or **after** below hooks (e.g. `before-existing-directory`)

Each internal plugin gets passed in `source` and `target` types on instantiation. `source` means the resolve hook that the plugin will execute against, in sequence. For a plugin that can satisfy the request, it will call the resolver's `doResolve` method w/ the `target` type ([source](https://github.com/webpack/webpack.js.org/issues/1458#issuecomment-330445790)).

## resolve

Starts resolving process

## parsedResolve

Parses parts of a request thru [ParsePlugin](https://github.com/webpack/enhanced-resolve/blob/master/lib/ParsePlugin.js), namely:

- the request path
- query string, if any
- whether the request is either a module, directory, or file

## describedResolve

- resolves aliases w/ AliasPlugin and AliasFieldPlugin
- hands off module requests to `module` stage
- applies context to requests w/ JoinRequestPlugin

## rawModule
- appends file extensions to requests (see [ModuleAppendPlugin](https://github.com/webpack/enhanced-resolve/blob/master/lib/ModuleAppendPlugin.js))

## module

Applies modules directories (such as `node_modules`) as contexts to resolve requests against

## relative

Loads and adds description file data (such as from a `package.json`) to the `request` object passed thru `resolver.doResolve`

## describedRelative

Passes file requests to `raw-file` stage and directory requests to `directory` stage

## directory

Passes any existing directory requests to the `existing-directory` stage

## existingDirectory

If request for a directory, resolve the filenames in this directory using main fields defined in description files (e.g. `package.json`)

## undescribedRawFile

Contextualizes raw file requests then passes request to `raw-file` stage

## rawFile

Appends file extensions to file requests then hands off to `file` stage

## file

- Resolves file request aliases thru AliasPlugin and AliasFieldPlugin, which are then handed back to `resolve` stage
- Checks if files exists w/ FileExistsPlugin and sets `existing-file` as target

## existingFile

Hands off any existing files to `resolved` stage

## resolved

Hands off to resolver's `result` hook w/ ResultsPlugin