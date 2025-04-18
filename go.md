author: Keshav Italia
date: 18 April 2025
title: deadfish-in-go

```{=org}
#+filetags: :programming:
```
```{=org}
#+identifier: 20250418T101848
```
an implementation of
/home/kesh/Documents/notes/20250418T101923–deadfish\_~programming~.org
programming language in
/home/kesh/Documents/notes/20241017T104355–go-programming-language\_~programming~.org.
This was originally written in org-mode as a literate program example.

``` go
import (
    "fmt"
    "log"
    "os"
)

func read_file(file string) {
    content, err := os.ReadFile(file)
    if err != nil { log.Fatal(err) }
    v := 0
    for _, line := range content {
        v = interpret_line(v, string(line))
    }
}

func interpret_line(value int, line string) int {
    for _, c := range line {
        if c == 'i' { value+=1 } else
        if c == 'd' { value-=1 } else
        if c == 's' { value*=value } else
        if c == 'o' { fmt.Printf("%d", value) }
        if value == -1 || value == 256 {
            value = 0
        }
    }
    return value
}


func main() {
    interpret_line(0, "iissisdddddddddddddddddddddddddddddddddo")
}
```
