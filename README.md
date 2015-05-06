ICL
===

ICL (imos config language) is a language especially for configurations.
The language's goal is to replace config files written in JSON or original config languages.

Example
-------

```js
@flags = {
  l : bool = false : 'Alias of --long.'
  long : bool = l : 'List in long format.'
}

main : struct = std.main.command {
  binary = '/bin/ls'
  args = {
    l : bool = @flags.long
  }
  argv = @argv
  assert argv.length > 0 : 'At least one directory must be specified.'
} : 'List directory contents.'
```
