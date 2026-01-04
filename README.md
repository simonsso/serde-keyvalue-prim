serde-keyvalue-prim
===================

A lightweight serde deserializer for strings containing key-value pairs separated by commas, as
commonly found in command-line parameters  or colon and semicolons as in simple line-based communication protocols.

Say your program takes a command-line option of the form:

```text
--foo type=bar,active,nb_threads=8
```

or you need to parse a configuration string like:

```text
type:bar;active:99;nb_threads=8
```

This crate provides a [from_key_values] function that deserializes these key-values into a
configuration structure. Since it uses serde, the same configuration structure can also be
created from any other supported source (such as a TOML or YAML configuration file) that uses
the same keys.

The deserializer supports parsing signed and unsigned integers, booleans, strings (quoted or
not), paths, and enums inside a top-level struct. The order in which the fields appear in the
string is not important.

See also, [source code]( https://github.com/simonsso/serde-keyvalue-prim)
[documentation](https://docs.rs/serde-keyvalue-prim)
[crates io](https://crates.io/crates/serde-keyvalue-prim)
### Acknowledgements 

This [project was forked from](https://crates.io/crates/serde-keyvalue) and [source](https://gitlab.com/BrightOpen/serde-keyvalue) then modified to support multiple delimiters.
