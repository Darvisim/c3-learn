---
title: "Asm Block"
slug: "asm block"
aliases:
 - "/More/14"
weight: 1
---
{{<start>}}
- Asm blocks uses a common grammar for all types of processors.
{{<end>}}

{{<defcod>}}
import std::io;

fn void main()
{
	int x = 3;
	
	io::printfn("%d", x);
	asm
	{
		xorl $eax,$eax;
		movl x,$eax;
	}
	io::printfn("%d", x);
}
{{</defcod>}}
