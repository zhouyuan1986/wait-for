## Wait for one or more service(s) to become available

`./wait-for` is a script designed to synchronize services like docker containers. It is [sh](https://en.wikipedia.org/wiki/Bourne_shell) and [alpine](https://alpinelinux.org/) compatible, and support configuring of multiple services. It was inspired by [vishnubob/wait-for-it](https://github.com/vishnubob/wait-for-it) and [mrako/wait-for](https://github.com/mrako/wait-for).

When using this tool, you only need to pick the `wait-for` file as part of your project.

## Usage

```
./wait-for host:port [-t timeout] [-- command args]
  -q | --quiet                        Do not output any status messages
  -t TIMEOUT | --timeout=timeout      Timeout in seconds, zero for no timeout
  -- COMMAND ARGS                     Execute command with args after the test finishes
```

## Examples

To check if [eficode.com](https://eficode.com) is available:

```
$ ./wait-for www.eficode.com:80 -- echo "Eficode is up"
Eficode is up
```

To check if [amazon](https://www.amazon.com) and [imdb](https://www.imdb.com) are available:

```
$ ./wait-for www.amazon.com:80 www.imdb.com:80 -- echo "amazon, imdb are all up"
amazon, imdb are all up
```
