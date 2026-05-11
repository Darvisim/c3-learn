---
title: "Foreach"
slug: "foreach"
aliases:
 - "/Basics/6"
weight: 6
---
{{<start>}}
- Use `foreach` to iterate over any collection (array, subarray, vector or any customized type implementing the indexing operators)
- `foreach_r` conversely allows iteration from back and forward.
- Either iterate over the value: `foreach (v : values)` or over index + value: `foreach (index, v : values)`
- Values can also be retrieved by reference by using `&` in front of the variable name: `foreach (&v : values)`, this allows mutation of the element directly.
{{<end>}}

{{<defcod>}}
import std::io;

fn void test(float[] values)
{
	io::printn("Forward");
	foreach (index, value : values)
	{
		io::printfn("%d: %f", index, value);
	}
	io::printn("Back");
	foreach_r (index, value : values)
	{
		io::printfn("%d: %f", index, value);
	}
}

fn void main()
{
	test({ 3.2, 5.0, 1.5, 7.135});
}
{{</defcod>}}
