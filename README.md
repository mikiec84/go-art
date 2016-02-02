# what

An Adaptive Radix Tree is an indexing data structure similar to traditional radix trees, but uses internal nodes that grow and shrink intelligently with consecutive inserts and removals.

Adaptive Radix Trees have many interesting attributes that could be seen as improvements on other indexing data structures like Hash Maps or other Prefix Trees, such as:

  - Worst-case search complexity of O(k), where `k` is the length of the key.
  - They don't have to be rebuilt due to excessive inserts.
  - The structure of their inner nodes is space-efficent when compared to traditional Prefix Trees.
  - They provide prefix compression, a technique where each inner node specifies how far to 'fast-forward' in the search key before traversing to the next child. 

# usage

Include `go-art` in your go pacakages with:

```
import( "github.com/kellydunn/go-art" )
```

Go nuts:

```
// Make an ART Tree
tree := art.NewTree()

// Insert some stuff
tree.Insert([]byte("art trees"), []byte("are rad"))

// Search for a key, and get the resultant value
res := tree.Search([]byte("art trees"))

// Inspect your result!
fmt.Printf("%s\n", res) // "are rad"
```
This fork makes all values in the ART nodes strings.
