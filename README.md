- š Hi, Iām @wvennm
- š Iām interested in ...
- š± Iām currently learning ...
- šļø Iām looking to collaborate on ...
- š« How to reach me ...

<!---
wvennm/wvennm is a āØ special āØ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
package zalgo_test

import (
    "fmt"
    "github.com/kortschak/zalgo"
    "os"
)

const invoke = `W.vennm
`

func Example_1() {
    z := zalgo.NewCorrupter(os.Stdout)

    z.Zalgo = func(n int, r rune, z *zalgo.Corrupter) bool {
        z.Up += 0.1
        z.Middle += complex(0.01, 0.01)
        z.Down += complex(real(z.Down)*0.1, 0)
        return false
    }

    z.Up = complex(0, 0.2)
    z.Middle = complex(0, 0.2)
    z.Down = complex(0.001, 0.3)

    fmt.Fprintln(z, invoke)

    // Output:
    // Eternal happiness.
}
