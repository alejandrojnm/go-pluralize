
# Go pluralize

This library is used to pluralize any string based on the number of elements of the slice passed to it.


## Installation 

to install this lib yopu need run this

```bash 
  go get github.com/alejandrojnm/go-pluralize
```
    
## Usage/Examples

```go
package main

import (
	"fmt"
	pluralize "github.com/alejandrojnm/go-pluralize"
)

func main() {
    slice := []string{"1"}
    word := "car"
    fmt.Printf("There is (%v) %s in the garage", len(slice), pluralize.Pluralize(len(slice), word))
}
```

The output for that will be 

`There is (1) car in the garage`

Return a plural suffix if the value is not 1, '1', or an object of length 1. By default, use 's' as the suffix:
* If value is 0, pluralize.Pluralize(0, "vote") display "votes".
* If value is 1, pluralize.Pluralize(1, "vote") display "vote".
* If value is 2, pluralize.Pluralize(2, "vote") display "votes".

If an argument is provided, use that string instead:
* If value is 0, pluralize.Pluralize(0, "class", "es") display "classes".
* If value is 1, pluralize.Pluralize(1, "class", "es") display "class".
* If value is 2, pluralize.Pluralize(2, "class", "es") display "classes".

If the provided argument contains a comma, use the text before the comma for the singular case and the text after the comma for the plural case:
* If value is 0, pluralize.Pluralize(0, "cand", "y,ies") display "candies".
* If value is 1, pluralize.Pluralize(1, "cand", "y,ies") display "candy".
* If value is 2, pluralize.Pluralize(2, "cand", "y,ies") display "candies".