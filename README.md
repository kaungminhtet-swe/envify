# envify

A simple and lightweight `.env` loader for Go applications. `envify` helps manage environment variables by loading them from a `.env` file into your Go program seamlessly.

## Features

- Load environment variables from a `.env` file automatically
- Override existing environment variables
- Lightweight and easy to use
- Works seamlessly with Go applications

## Getting Started

### Installation

With [Go module](https://github.com/golang/go/wiki/Modules) support, simply add the following import:

```go
import "github.com/mr-kmh/envify"
```

Then, run the following command to install `envify`:

```sh
$ go get -u github.com/mr-kmh/envify
```

### Usage

Create a `.env` file in your project root:

```
VARIABLE=Hello, Envify!
PORT=8080
DEBUG=true
```

Now, use `envify` in your Go application:

```go
package main

import (
	"fmt"
	"os"

	"github.com/mr-kmh/envify"
)

func init() {
	envify.Load() // Load environment variables from .env
}

func main() {
	fmt.Println("VARIABLE:", os.Getenv("VARIABLE"))
	fmt.Println("PORT:", os.Getenv("PORT"))
	fmt.Println("DEBUG:", os.Getenv("DEBUG"))
}
```

### Running the Application

Use the Go command to run the program:

```sh
$ go run main.go
```

If your `.env` file contains:

```
VARIABLE=Hello, Envify!
PORT=8080
DEBUG=true
```

The output will be:

```
VARIABLE: Hello, Envify!
PORT: 8080
DEBUG: true
```

## API Reference

### `envify.Load(filepath ...string)`

Loads environment variables from a `.env` file.

- **filepath (optional)**: Path to the `.env` file. If not specified, it defaults to `./.env`.
- **Panic on error**: An `error` if the file cannot be read.

## Contributing

Contributions are welcome! Feel free to submit issues and pull requests.

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.

