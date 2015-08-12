<!-- AUTOGENERATED. See 'doc/build.jl' for source. -->
*LightGraphs.jl* includes the following distance measurements:

### eccentricity
```
1  eccentricity(g::Union{LightGraphs.DiGraph,LightGraphs.Graph})
2  eccentricity(g::Union{LightGraphs.DiGraph,LightGraphs.Graph}, v::Int64)
3  eccentricity{T}(g::Union{LightGraphs.DiGraph,LightGraphs.Graph}, v::Int64, distmx::AbstractArray{T,2})
4  eccentricity(g::Union{LightGraphs.DiGraph,LightGraphs.Graph}, vs::AbstractArray{Int64,1})
5  eccentricity{T}(g::Union{LightGraphs.DiGraph,LightGraphs.Graph}, vs::AbstractArray{Int64,1}, distmx::AbstractArray{T,2})
6  eccentricity{T}(g::Union{LightGraphs.DiGraph,LightGraphs.Graph}, distmx::AbstractArray{T,2})
```
*Source: [1](https://github.com/JuliaGraphs/LightGraphs.jl/tree/ee65811af7056c6ae43447a6c983a6d9708bf0cf/src/distance.jl#L41) [2](https://github.com/JuliaGraphs/LightGraphs.jl/tree/ee65811af7056c6ae43447a6c983a6d9708bf0cf/src/distance.jl#L35) [3](https://github.com/JuliaGraphs/LightGraphs.jl/tree/ee65811af7056c6ae43447a6c983a6d9708bf0cf/src/distance.jl#L35) [4](https://github.com/JuliaGraphs/LightGraphs.jl/tree/ee65811af7056c6ae43447a6c983a6d9708bf0cf/src/distance.jl#L41) [5](https://github.com/JuliaGraphs/LightGraphs.jl/tree/ee65811af7056c6ae43447a6c983a6d9708bf0cf/src/distance.jl#L41) [6](https://github.com/JuliaGraphs/LightGraphs.jl/tree/ee65811af7056c6ae43447a6c983a6d9708bf0cf/src/distance.jl#L48)*.

Calculates the eccentricity[ies] of a vertex `v`, vertex vector `vs`, or the entire graph. An optional matrix of edge distances may be supplied.

The eccentricity of a vertex is the maximum shortest-path distance between it and all other vertices in the graph.

Because this function must calculate shortest paths for all vertices supplied in the argument list, it may take a long time.

The output is either a single float (when a single vertex is provided) or a vector of floats corresponding to the vertex vector. If no vertex vector is provided, the vector returned corresponds to each vertex in the graph.

Note: the eccentricity vector returned by `eccentricity()` may be used as input for the rest of the distance measures below. If an eccentricity vector is provided, it will be used. Otherwise, an eccentricity vector will be calculated for each call to the function. It may therefore be more efficient to calculate, store, and pass the eccentricities if multiple distance measures are desired.

### radius
```
1  radius{T}(all_e::Array{T,1})
2  radius(g::Union{LightGraphs.DiGraph,LightGraphs.Graph})
3  radius{T}(g::Union{LightGraphs.DiGraph,LightGraphs.Graph}, distmx::AbstractArray{T,2})
```
*Source: [1](https://github.com/JuliaGraphs/LightGraphs.jl/tree/ee65811af7056c6ae43447a6c983a6d9708bf0cf/src/distance.jl#L69) [2](https://github.com/JuliaGraphs/LightGraphs.jl/tree/ee65811af7056c6ae43447a6c983a6d9708bf0cf/src/distance.jl#L70) [3](https://github.com/JuliaGraphs/LightGraphs.jl/tree/ee65811af7056c6ae43447a6c983a6d9708bf0cf/src/distance.jl#L70)*.

Returns the minimum eccentricity of the graph.

### diameter
```
1  diameter{T}(all_e::Array{T,1})
2  diameter(g::Union{LightGraphs.DiGraph,LightGraphs.Graph})
3  diameter{T}(g::Union{LightGraphs.DiGraph,LightGraphs.Graph}, distmx::AbstractArray{T,2})
```
*Source: [1](https://github.com/JuliaGraphs/LightGraphs.jl/tree/ee65811af7056c6ae43447a6c983a6d9708bf0cf/src/distance.jl#L52) [2](https://github.com/JuliaGraphs/LightGraphs.jl/tree/ee65811af7056c6ae43447a6c983a6d9708bf0cf/src/distance.jl#L53) [3](https://github.com/JuliaGraphs/LightGraphs.jl/tree/ee65811af7056c6ae43447a6c983a6d9708bf0cf/src/distance.jl#L53)*.

Returns the maximum eccentricity of the graph.

### center
```
1  center{T}(all_e::Array{T,1})
2  center(g::Union{LightGraphs.DiGraph,LightGraphs.Graph})
3  center{T}(g::Union{LightGraphs.DiGraph,LightGraphs.Graph}, distmx::AbstractArray{T,2})
```
*Source: [1](https://github.com/JuliaGraphs/LightGraphs.jl/tree/ee65811af7056c6ae43447a6c983a6d9708bf0cf/src/distance.jl#L77) [2](https://github.com/JuliaGraphs/LightGraphs.jl/tree/ee65811af7056c6ae43447a6c983a6d9708bf0cf/src/distance.jl#L81) [3](https://github.com/JuliaGraphs/LightGraphs.jl/tree/ee65811af7056c6ae43447a6c983a6d9708bf0cf/src/distance.jl#L81)*.

Returns the set of all vertices whose eccentricity is equal to the graph's radius (that is, the set of vertices with the smallest eccentricity).

### periphery
```
1  periphery{T}(all_e::Array{T,1})
2  periphery(g::Union{LightGraphs.DiGraph,LightGraphs.Graph})
3  periphery{T}(g::Union{LightGraphs.DiGraph,LightGraphs.Graph}, distmx::AbstractArray{T,2})
```
*Source: [1](https://github.com/JuliaGraphs/LightGraphs.jl/tree/ee65811af7056c6ae43447a6c983a6d9708bf0cf/src/distance.jl#L61) [2](https://github.com/JuliaGraphs/LightGraphs.jl/tree/ee65811af7056c6ae43447a6c983a6d9708bf0cf/src/distance.jl#L65) [3](https://github.com/JuliaGraphs/LightGraphs.jl/tree/ee65811af7056c6ae43447a6c983a6d9708bf0cf/src/distance.jl#L65)*.

Returns the set of all vertices whose eccentricity is equal to the graph's diameter (that is, the set of vertices with the largest eccentricity).

