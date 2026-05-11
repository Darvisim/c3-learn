---
title: "Nextcase"
slug: "nextcase"
aliases:
 - "/Basics/9"
weight: 9
---
{{<start>}}
- Use `nextcase` to fallthrough to the next statement.
- Empty case statements have implicit fallthrough.
{{<end>}}

{{<defcod>}}
import std::io;

fn void main()
{
	String s = "Gone--";

	switch (s)
	{
		case "Python":
			io::printf("Far from ");
			nextcase "C3";
		case "OOP++":
			io::printf("Definitely not ");
			nextcase;
		case "C3":
		case "C":
			io::printfn("OK");
		default:
			io::printf("Most likely not ");
			nextcase "C3";
	}
}
{{</defcod>}}
