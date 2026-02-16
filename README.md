# lru

A thread-safe LRU (Least Recently Used) cache implementation for Go with generic value support.

## Features

- Thread-safe concurrent access using read-write locks
- Generic type support for type-safe caching
- Lazy value construction with error handling
- Automatic eviction of least recently used entries
- Simple and efficient API

## Installation

```bash
go get github.com/kode4food/lru
```

## Usage

```go
import "github.com/kode4food/lru"

// Create a cache with max size of 100 entries
cache := lru.NewCache[string](100)

// Get or create an entry
value, err := cache.Get("key", func() (string, error) {
    // This constructor is only called on cache miss
    return "computed value", nil
})
```

## License

MIT License - see LICENSE.md for details
