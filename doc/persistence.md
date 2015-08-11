## Writing a Graph
Graphs may be written to I/O streams and files using the `write` function:

{{write}}

## Reading a Graph From a File
Graphs stored using the `write` functions above may be loaded using `readgraph`:

{{readgraph, readgraphml, readgml}}

## Examples
```julia
julia> write(STDOUT, g)
julia> write(g, "mygraph.jgz")
julia> g = readgraph("mygraph.jgz")
julia> g = readgraphml("mygraph.xml")
julia> g = readgml("mygraph.gml")
```