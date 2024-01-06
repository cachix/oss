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
