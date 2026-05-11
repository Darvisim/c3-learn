---
title: "Switch"
slug: "switch"
aliases:
 - "/Basics/8"
weight: 8
---
{{<start>}}
- `case` statements automatically break.
{{<end>}}

{{<defcod>}}
import std::io;
import std::core::env;

fn void main()
{
	io::printf("It's crucial to say ");
	switch (env::OS_TYPE)
	{
		case WIN32:
			io::printf("WNU-");
		case LINUX:
			io::printf("GNU-");
		case MACOS:
			io::printf("MNU-");
		default:
			io::printf("DUNNO-");
	}
	io::printfn("Linux.");
}
{{</defcod>}}
