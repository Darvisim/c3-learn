---
title: "Short Function Syntax"
slug: "short function syntax"
aliases:
 - "/More/30"
weight: 17
---
{{<start>}}
- Rather than using `{}` to define the function body, one can use `=> <expr>`.
- This behaves as if the function only contained a single return, returning the expression.
{{<end>}}

{{<defcod>}}
import std::io;

fn int square(int x) => x * x;
fn void printx(int x) => io::printfn("%d", x);

fn void main()
{
	printx(square(3));
}
{{</defcod>}}
