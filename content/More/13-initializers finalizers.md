---
title: "Initializers & Finalizers"
slug: "initializers finalizers"
aliases:
 - "/More/26"
weight: 13
---
{{<start>}}
- It is sometimes useful to run code at startup and shutdown. Static initializers and finalizers are special functions that are run at startup and shutdown respectively.
{{<end>}}

{{<defcod>}}
import std::io;

fn void hello() @init
{
	io::printf("hello");
}

fn void world() @finalizer
{
	io::printfn("world");
}

fn void main()
{
	io::printf(", ");
}
{{</defcod>}}
