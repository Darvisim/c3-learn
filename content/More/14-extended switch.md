---
title: "Extended Switch"
slug: "extended switch"
aliases:
 - "/More/27"
weight: 14
---
{{<start>}}
- It's possible to have an extended `switch`, which can take any type of conditionals.
{{<end>}}

{{<defcod>}}
import std::io;

fn bool is_odd(int x)
{
	return x % 2 == 1;
}

fn void main()
{
	int x = 2;

	switch
	{
	case x == 1:
		io::printfn("One");
	case is_odd(x):
		io::printfn("Odd");
	case x < 0:
		io::printfn("Negative");
	case x == 0:
		io::printfn("Zero");
	default:
		io::printfn("Number was: %d", x);
	}
}
{{</defcod>}}
