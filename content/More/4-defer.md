---
title: "Defer"
slug: "defer"
aliases:
 - "/More/17"
weight: 4
---
{{<start>}}
- Defer will be invoked on scope exit.
- `defer catch` is a version of defer that only runs when the macro or function returns a fault.
- `defer try` is similar, but only runs on a result return.
{{<end>}}

{{<defcod>}}
import std::io;

fn void main()
{
	defer io::printfn("world");
	io::print("hello, ");
}
{{</defcod>}}
