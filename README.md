## Doubloon 
Reflective DLL injection and stack spoofing, written in Go.

## Build Process
This project was designed to be built on Linux and used on Windows targets.
```bash
make clean && make all
```
## Technical Information
This program works by injecting the locally compiled DLL under payloads, into a running process and executing it. It does this using `go generate` and `go build` to statically integrate the shellcode into the injector (this means it is an unstaged virus).

The main function, simply generates/locates a process to inject into, reflectively maps the DLL into that process' memory, and terminates after executing the DLL's `.text` section.
