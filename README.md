# cpm_40.2_repro

Run `cmake -S verify/ -B build` in the root of the project to see the error.

The `SOURCE_SUBDIR` isn't being properly added to the `<NAME>_SOURCE_DIR` variable,
which causes projects to break since `<NAME>_SOURCE_DIR` is a variable
that the `project()` command also generates ( if it doesn't already exist ).
