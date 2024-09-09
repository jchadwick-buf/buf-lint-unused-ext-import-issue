This repo contains a buf module that return the following protoc-gen-buf-lint errors:

```log
--buf-lint_out: test/c.proto:5:1:Import "test/a.proto" is unused.
```

However, the import *is* used and removing it creates a reference error.

Reproduce using
```sh
protoc -I ../protovalidate -I . --buf-lint_out=. $(find ./test -name '*.proto')
```