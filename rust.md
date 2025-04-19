author: Keshav Italia
date: 18 April 2025
title: deadfish-in-rust

```{=org}
#+filetags: :programming:
```
```{=org}
#+identifier: 20250418T104700
```
an implementation of the
/home/kesh/Documents/notes/20250418T101923–deadfish\_~programming~.org
language in
/home/kesh/Documents/notes/20240828T123235–rust-programming-language\_~programming~.org.
This file was used in a demo to show emacs' advanced integrations with
llms

``` rust
fn interpret_line(value: i32, line: &str) -> i32 {
    let mut value = value;
    for c in line.chars() {
        match c {
            'i' => value += 1,
            'd' => value -= 1,
            's' => value *= value,
            'o' => println!("{}", value),
            _ => (),
        }
        if value == -1 || value == 256 {
            value = 0;
        }
    }
    return value;
}

fn main() {
    let s = "iissisdddddddddddddddddddddddddddddddddo";
    interpret_line(0, s);
}
```
