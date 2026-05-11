---
title: "Default Arguments"
slug: "default arguments"
aliases:
 - "/More/15"
weight: 2
---
{{<start>}}
- C3 allows use of default arguments.
{{<end>}}

{{<defcod>}}
import std::io;

fn void test(int x = 1)
{
	io::printfn("%d", x);
}

fn void main()
{
	test();
	test(100);
}
{{</defcod>}}
