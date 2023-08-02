https://ocaml.org/install

```shell
bash -c "sh <(curl -fsSL https://raw.githubusercontent.com/ocaml/opam/master/shell/install.sh)"
```
[/usr/local/bin] -> opam package manager install path

```shell
opam init
```

update paths in ~/.zshrc
update current shell env
```shell
eval $(opam env --switch=default)
```

Setup OCaml Development Environment
```shell
opam install dune merlin ocaml-lsp-server odoc ocamlformat utop dune-release
```

Link Merlin with editor
```shell
opam user-setup install
```

Using the REPL
```shell
utop
```
Exit the REPL
```shell
exit 0;;
```


### Starting a new project
```shell
dune init project helloworld
```
All the metadata of your project is available in the file `dune-project`. Edit it to match your specific project.

We can build our program with `dune build`, which creates an executable file:
```shell
dune build
```

To run the program, we can use:
```shell
dune exec ./bin/main.exe
```
Or alternatively
```shell
dune exec helloworld
```

Configure OCamlFormat to format your code
```
echo "version = `ocamlformat --version`" > .ocamlformat
```

In addition to the editor, Dune is also able to drive OCamlFormat. Running this command will automatically format all files from your codebase:
```
dune fmt
```

### Generate documentation with odoc
`odoc` is a tool that is not meant to be used by hand, just as compilers are not meant to be run manually in complex projects. Dune can drive `odoc` to generate documentation in the form of HTML, LaTeX, or man pages, from the docstrings and interface of the project's modules.

The following command will generate the documentation as HTML:
```
dune build @doc

# Unix or macOS
open _build/default/_doc/_html/index.html
```

# Resources
- **OCaml First Steps**
(https://ocaml.org/docs/up-and-running#first-steps-with-ocaml)
- **OCaml Manual**
(https://v2.ocaml.org/manual/index.html)
- **Real World OCaml**
(https://dev.realworldocaml.org/index.html)
- **Dune**
(https://dune.readthedocs.io/en/stable/)



