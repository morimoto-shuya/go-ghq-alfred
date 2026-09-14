# go-ghq-alfred

![](https://github.com/pddg/go-ghq-alfred/workflows/test/badge.svg?branch=master)

Search local repos with ghq in Alfred Workflow.

## Environment

* Alfred 3.4 (or later)
* [ghq](https://github.com/motemen/ghq)

## Usage

This tool is a CLI tool. Output JSON strings.

```bash
$ ./go-ghq-alfred '{query}' $(ghq list -p)
```

Repository paths can also be read from standard input. This avoids shell argument
length limits when you have many repositories.

```bash
$ ghq list -p | ./go-ghq-alfred '{query}'
```

## In Alfred

This workflow start with `ghq {query}` in alfred.  

The workflow runs `ghq list -p` once when the search starts, then Alfred filters
the returned repositories as you type. This keeps incremental search responsive
even with a large repository list.

### Preparing

You should specify path to `ghq`. Open this workflow settings, and edit environment variables. Default is `/usr/local/bin/ghq`.  

And I recommend you to specify a editor and terminal app. Default is `Visual Studio Code.app` and `iTerm.app`

### Modifier key options

* **Enter**: Open repository in Finder.
* **Shift + Enter**: Open repository in your default browser.
* **Command + Enter**: Same as Enter only.
* **Option + Enter**: Search "user/repo" in google.
* **Fn + Enter**: Open repository in your terminal.
* **Control + Enter**: Open repository in your editor.

## Build

```bash
$ mise run test
$ mise run build
$ mise run dist
```

## Attributes

Icons provided by www.flaticon.com.

### github and git logo

Icon made by Freepik from www.flaticon.com

### bitbucket logo

Icon made by Swifticons from www.flaticon.com

## Author

morimoto-shuya

## License

MIT
