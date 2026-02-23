---
title: "Strings"
slug: "strings"
weight: 14
---
{{<start>}}
ZString -> String (view, no copy)
```c3 {norun=true}
import std::io;

fn void demo_z_to_s()
{
	ZString z = "Hello";
	assert(z[z.len()] == '\0'); // The ZString ends in '\0'
	String s = z.str_view();

	io::printfn("%s", s);
}
```
String -> ZString
```c3 {norun=true}
import libc;

fn void demo_s_to_z()
{
	String s  = "Hello";
	ZString z = s.zstr_copy(mem); // '\0' will be here

	// C call which needs zero-terminated char*
	libc::puts(z);
}
```
DString -> String
```c3 {norun=true}
import std::io;
 
fn void demo_ds_to_s() {
	DString ds = dstring::new(mem, "C3");
	// view (no copy, will be freed when the dstring is freed)
	String v = ds.str_view();
	// independent copy
	String c = ds.copy_str(mem);

	ds.free(); // v is now invalid
	io::printfn(c);
}
```
String -> DString
```c3 {norun=true}
fn void demo_s_to_ds()
{
	String s = "C3 rocks";
	DString ds = dstring::new(mem, s);
	ds.append_string("!"); // example of dstring append method
}
```
{{<end>}}

{{<defcod>}}
import std::io;

fn void main()
{
	ZString z = "Hello";
	String s = z.str_view();
	io::printfn("%s", s);
}

{{</defcod>}}
