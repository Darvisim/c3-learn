---
title: "Modules & Namespacing"
slug: "modules"
aliases:
 - "/Basics/1"
 - "/Basics/2"
 - "/Basics/imports"
weight: 1
---

{{<toc>}}

# Modules

C3 groups functions, types, variables and macros into namespaces called modules,
each made of one or more module sections. A module section is declared with the
`module` keyword followed by the module path; module sections have access
to all declarations from other module sections in the same module, but their
imports are separate.

```c3
module example;

String name = "User";

module example;
import other::submodule;

fn void main()
{
	submodule::greet(name);
}

module other::submodule;
import std::io;

fn void greet(String name)
{
	io::printfn("Hello %s!", name);
}
```

If a file does not start with the `module` keyword the module name will be
inferred as the file name, converted to lower case, with any invalid characters
replaced with underscores; however if this is done the file cannot contain any
other module declarations.

Modules are entirely separate from the filesystem layout, you can split a single
module into multiple sections in different files or put multiple modules in the
same file if needed.

# Imports

Modules are imported using the `import` keyword. Submodules are recursively
imported by default; while this does allow importing the entire stdlib with
`import std;`, it is recommended to be more descriptive with imports for
clarity.

Path shortening is supported so imported functions, macros, values, and
constants can be used with only one level of the module path as long as
it is unambiguous, and types can be used without a module path.

C3's recommended code style uses only a single path level for functions and
no path for types, but any level can be used.

```c3
import std::io;

fn void main()
{
	std::io::printn("Full path");
	io::printn("Shortened path");

	std::io::file::exists("Automatically imported submodule");
	io::file::exists("Shorter path");
	file::exists("Shortest path");

	std::io::File a; // :(
	io::File b;
	File c; // :)
}
```


