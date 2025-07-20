# Go Packages & Executable Code

## ✅ Key Rules in Go

- If you want to write **executable code**, it **must** be in the `main` package.

- All files belonging to the **same directory** should belong to the **same package**.

- The **name of the directory** and the **package** does **not have to be the same**, but:
  - All files under the same directory **must** use the **same package name**.

- Files with the `package main` will **automatically execute** the `main()` function without calling it manually.

- Any other package (not `main`) requires **manual function invocation** from another file that imports it.

---

## ❌ Non-Executable Package Example
❌ If you write:

package xyz

func main() {
	fmt.Println("Hello from xyz")
}
And try to run it using:
go run yourfile.go

It will not run — and you'll get an error like:
go run: cannot run non-main package

✅ To run code directly using go run, you must use:

package main

func main() {
	fmt.Println("This will run ✅")
}
- 🔎 Why?
```
Only package main is treated as a runnable program

All other package names (like xyz, utils, maths, etc.) are treated as library/utility packages

They are intended to be imported into other programs, not executed directly
```

- Go **does not allow you to access a function from another package unless it is exported.

- In Go, a name (function, variable, struct, etc.) is exported only if it starts with an **uppercase** letter.

- You import using the module name (go mod init mylearning, command executed for creating go.mod) here mylearning is the name of the project/module. 

### SYNTAX:
- import module_name/package_name

- For using the functions of the imported package, package_name.function_name(arguments)

### CODE:
import (
	"fmt"
	"mylearning/utils"
)

func main() {
	fmt.Println("Hello World")
	utils.Myutils("Importing other packages")
}

