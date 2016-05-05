# flatmap
flatmap transform nested map to flatten map

# How to use?

```
package main

import (
    "fmt"
	"log"

	"github.com/astaxie/flatmap"
)

func main() {
	mp := map[string]interface{}{
		"foo": struct {
			Name string
			Age  int
		}{
			"astaxie",
			30,
		},
	}
	fm, err := flatmap.Flatten(mp)
	if err != nil {
		log.Fatal(err)
	}
	fmt.Println(fm)
    // Output map[foo.Name:astaxie foo.Age:30]
}

```