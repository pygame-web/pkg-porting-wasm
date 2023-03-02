# pkg-porting-wasm
Tracks porting efforts on some modules you'd like to have working in pygbag



How to proceed :
First check the existing package list **here** https://github.com/pygame-web/archives/tree/main/repo/pkg if proposed packages relies on other unavailable packages

https://pygame-web.github.io/wiki/pkg is a smaller list of what has been already tested and is considered useable on python-wasm.  [Packages to test are listed here](https://github.com/pygame-web/pkg-porting-wasm/issues?q=is%3Aissue+is%3Aopen+label%3A%22AVAIL+FOR+TESTING%22)

Please help fill up https://pygame-web.github.io/wiki/pkg when you find that a package is working well ( modified or not ).


go here https://github.com/pygame-web/pkg-porting-wasm/issues

open a issue there begin with package name on pypi, or toplevel import and both pypi project page and git url in description

with maybe a log of what happened when you tried to run it on web.

eg https://github.com/pygame-web/pkg-porting-wasm/issues/3


When testing a module with pygbag runtime :

- if tested modules are in a subfolder "modules" use sys.path.add("modules") before importing them.
- Do not forget to put **all** non stdlib imports at top of main.py and in order, including those made by submodules.
- The async import of pygbag runtime is a hack, driven by ast module + main.py with no re ordering .
- Pypi does not provide a deps table, pyodide's one is borrowed but won't cover new modules manually added.


