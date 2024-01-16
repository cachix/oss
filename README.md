Here are the issues from open source that require basic Haskell skills:

- https://github.com/agrafix/elm-bridge/pull/53#issuecomment-1877219709

- Port this snippet to Servant

```haskell

jsonError :: (ToJSON a) => ServerError -> a -> ServerError
jsonError err json =
  err
    { errBody = encode json,
      errHeaders = [jsonHeader]
    }
  where
    jsonHeader =
      ( "Content-Type",
        "application/json;charset=utf-8"
      )

```

Here are issues from open source that requires advanced Haskell knowledge and possiblly other devops areas:

- [ghcid leaves dangling processes on shutdown](https://github.com/ndmitchell/ghcid/issues/257), investigate [this solution](https://github.com/acondolu/ghcid/commit/d299f9a4cbdf7a2278d7c5b1be03adfeb4cc195b)
