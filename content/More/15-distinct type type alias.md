---
title: "Distinct Types & Type Aliases"
slug: "distinct type type alias"
aliases:
 - "/More/28"
weight: 15
---
{{<start>}}
- Uses the uniform `alias` syntax.
- Regular type aliases are the same as C `typedef`, C3 `typedef` creates a distinct type.
- Distinct types are type aliases that doesn't implicitly convert to the aliased type.
- `typedef inline` types can automatically convert to their underlying type and inherit the methods of their underlying type, but otherwise work as distinct types.
- By default constants of the underlying type have to be cast to a distinct type, but using the `@constinit` attribute will allow implicit conversion.
{{<end>}}

{{<defcod>}}
import std::io;

alias MyInt = int;
typedef MyId @constinit = int;
typedef StrongId = int;

fn void main()
{
	MyInt x = 27;
	MyId y = 3;
	int a = x;
	StrongId b = (StrongId)42; // An explicit cast is required

	// int c = y; <- This doesn't work

	// Explicit conversion works
	x += (int)y;

	io::printfn("%s %s", y, x);
}
{{</defcod>}}
