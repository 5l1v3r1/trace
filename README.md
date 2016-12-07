System tracer in Rust

The system tracer will show all syscalls (and assembly) that is being executed. This allows tracing of complete program flows. Tracer can be run for new processes, but also be attached to existing processes.

# Usage

## Start a new process

`sh
cargo run -- -a -c "/bin/ls"
`

## Connect to an existing process

`sh
cargo run -- -a --pid 0
`

## References

* http://system.joekain.com/2015/07/15/rust-load-and-ptrace.html
* http://eli.thegreenplace.net/2011/01/23/how-debuggers-work-part-1
* https://github.com/hoelzro/rust-execution-tracer/blob/master/posix.rs
* https://github.com/eliben/pyelftools/blob/5d3b1545df30d4bc3a6cfa8741b1f08cb6bf204b/elftools/elf/elffile.py
* http://man7.org/linux/man-pages/man5/proc.5.html
* http://www.tldp.org/LDP/LG/issue85/sandeep.html
* https://github.com/larsbergstrom/rust-egl/blob/master/test/egl-android-glue/jni/android-dl.cpp
* https://opensource.apple.com/source/gdb/gdb-908/src/binutils/readelf.c
* http://www.sco.com/developers/gabi/1998-04-29/ch4.eheader.html
* https://grugq.github.io/docs/subversiveld.pdf
* http://lxr.free-electrons.com/source/include/uapi/linux/elf.h#L277
* http://www.tldp.org/LDP/LG/issue85/sandeep.html

## TODO

* libbacktrace
* add dwarf support
* parse arguments, file get x64
* diff changed register
* check repetitions
* disable colorcoding when piping
* searching
* filtering
* all params
* ptrace_syscall flag?
* PT_DENY_ATTACH
* dl_addr
* /proc/%d/mem
* /proc/%d/maps
* https://github.com/djpnewton/libcorkscrew_ndk/blob/master/ptrace.c
* load_symbol_table
* http://osxr.org:8080/android/source/system/core/libcorkscrew/symbol_table.c
* load_ptrace_context