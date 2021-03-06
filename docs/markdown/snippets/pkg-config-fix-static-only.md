## Improved generation of pkg-config files for static only libraries.

Previously pkg-config files generated by the pkgconfig modules for static libraries
with dependencies could only be used in a dependencies with `static: true`.

Now the generated file contains the needed dependencies libraries directly within
`Requires` and `Libs` for build static libraries passed via the `libraries` keyword
argument.

Projects that install both a static and a shared version of a library should use
the result of `both_libraries` to the pkg config file generator or use
configure_file for more complicated setups.
