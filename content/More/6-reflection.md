---
title: "Reflection"
slug: "reflection"
aliases:
 - "/More/19"
weight: 6
---
{{<start>}}
- There are several built-in functions to inspect the code during compile time.
- `.len` on arrays and slices returns their length.
- `$defined(<expr>)` returns true if the expression inside is defined.
- `$reflect(<identifier>)` returns a struct containing information about the identifier, often including the following properties:
  - `.size`: the size of the value in bytes, the stdlib provides the `@sizeof(x)` macro as a shorthand for `$reflect(x).size`.
  - `.alignment`: the alignment of the value in bytes, the stdlib provides `@alignof(x)` as a shorthand.
  - `.qname`: the qualified name of the identifier, e.g `std::io::printf`. The stdlib provides `@qnameof(x)` as a shorthand.
  - `.name`: the base name of the identifier, e.g. `printf`. The stdlib provides `@nameof(x)` as a shorthand.
- `$Typeof(<expr>)` returns the type of the expression.
- `$stringify(<expr>)` returns the expression as a string.
- `<type>::size` returns the size of a type.
- `<type>::align` returns the alignment of a type.
- `<type>::name` return the name of a type.

See https://c3-lang.org/generic-programming/reflection/ for the full details.
{{<end>}}

{{<defcod>}}
import std::io;

fn void main()
{
	int x;
	double y;

	if ($defined(z))
	{
		io::printfn("hello, world");
	}
	io::printfn($reflect(io::printfn).qname);
	io::printfn("%s %s", $reflect(x).size, @sizeof(y));
	io::printfn("sz has size: %d", sz::size);
}
{{</defcod>}}
