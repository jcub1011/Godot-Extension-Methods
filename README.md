Just copy the file into your project and you should be good.
Created for C# version 6.0 on Godot 4.0.

# Godot-Extension-Methods
Godot Extension Methods contains various extension methods I've found useful during game development.

## Installation
It's nothing complicated. Just download the NodeExtensions.cs file and copy it to your project.

## Provided Methods
### Node Extensions
Godot has several builtin methods for getting child objects, but I prefer Unity's approach to finding children. I've created various extensions that mimic how it works in Unity and added some more useful methods.

``` csharp
/// Gets all children of the given type via depth first search. 
/// Note: This function excludes children of a node that is the target type. 
/// See GetChildrenThorough() if you want that.
GetChildren<T>()

/// Gets all children of the given type via depth first search.
/// Note: This also includes children of a node that is the target type. 
/// See GetChildren() if you don't want that.
GetChildrenThorough<T>()

/// Gets the first child of the given type via breadth first search.
GetChild<T>()

/// Gets the first direct child fo the given type.
/// This is faster when you know the child you are searching for is a direct child.
GetDirectChild<T>()

/// Gets the direct children matching the type T. 
/// Faster than GetChildren() when you know the nodes are direct children.
GetDirectChildren<T>()

/// Gets the first sibling matching the type T, where it returns null if the sibling does not exist.
GetFirstSiblingOfType<T>()

/// Gets all of the siblings matching the type T.
GetFirstChildOfType<T>()
```

### Math Extensions
There are many useful math functions in Mathf but suprisingly, it was lacking a quadratic solver. Here's my implementation that gets both the negative and positive root.

``` csharp
/// Returns true if a non-complex solution exists.
QuadraticSolver(a, b, c, out negativeRoot, out positiveRoot)
```

### Other Extensions
There are several additional extensions included but, I decided they probably weren't important enough to list here. See the cs file to check them out.

### License
[MIT License](https://choosealicense.com/licenses/mit/)
