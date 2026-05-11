---
title: "If"
slug: "if"
aliases:
 - "/Basics/7"
weight: 7
---
{{<start>}}
{{<end>}}

{{<defcod>}}
import std::io;

fn void main()
{
	int x = 2;

	if (x == 1)
	{
		io::printfn("1");
	}
	else if (x == 2)
	{
		io::printfn("2");
	}
	else
	{
		io::printfn("0");
	}
}
{{</defcod>}}
