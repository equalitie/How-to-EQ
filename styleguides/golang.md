# Golang style guide

(There is none!)

The go toolchain features a `fmt` command that will automatically format your code
according to a particular style guide.  It is worth one's time to learn what the
rules the tool imposes are, but for the sake of maintaining a consistent style in
Go projects, the `fmt` tool should be used.

Perhaps the simplest thing to do is create a build script for your Go codebase
like the one
[used to build the CENO client](https://github.com/equalitie/ceno/blob/next/ceno-client/build.sh).
