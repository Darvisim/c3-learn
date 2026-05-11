---
title: "Structs & Unions"
slug: "structs unions"
aliases:
 - "/Basics/11"
weight: 11
---
{{<start>}}
- Names of user defined types like structs and unions must start with an uppercase letter.
- Structs and unions can be nested.
- Initialization follows C rules with `{ }`.
- Unlike C it's possible to reassign the value of a struct or union with `{ }` as well.
{{<end>}}

{{<defcod>}}
import std::io;

union Point
{
	// Nested struct
	struct
	{
		int x, y;
	}
	int[2] v;
}

fn void main()
{
	Point p = { 2, 3 };

	io::printfn("Point: %d, %d", p.x, p.y);
	// Reassign the p value using a literal and named arguments:
	p = { .v = { 5, -1 } };
	io::printfn("Point: %d, %d", p.x, p.y);
}
{{</defcod>}}
