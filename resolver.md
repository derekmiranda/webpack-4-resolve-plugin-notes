# Resolver API

## doResolve

**Parameters**: hook, request, message, resolveContext, callback

1.  Calls `resolve-step` hook w/ hook and request

## ensureHook

**Parameters**: name

Ensures a hook exists on the resolver Tapable instance

- if a hook doesn't exist yet for the passed-in name, creates an AsyncSeriesBailHook for that name

## getHook

**Parameters**: name

Gets Tapable hook instance associated w/ `name`
