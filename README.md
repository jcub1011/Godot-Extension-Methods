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
public static List<T> GetChildren<T>(this Node node) where T : class {}

/// Gets all children of the given type via depth first search.
/// Note: This also includes children of a node that is the target type. 
/// See GetChildren() if you don't want that.
public static List<T> GetChildrenThorough<T>(this Node node) where T : class {}

/// Gets the first child of the given type via breadth first search.
public static T GetChild<T>(this Node node) {}

/// Gets the first direct child fo the given type.
/// This is faster when you know the child you are searching for is a direct child.
public static T GetDirectChild<T>(this Node node) where T : class {}

/// Gets the direct children matching the type T. 
/// Faster than GetChildren() when you know the nodes are direct children.
public static List<T> GetDirectChildren<T>(this Node node) where T : class {}

/// Gets the first sibling matching the type T, where it returns null if the sibling does not exist.
public static T GetFirstSiblingOfType<T>(this Node node) where T : class {}

/// Gets all of the siblings matching the type T.
public static List<T> GetSiblingsOfType<T>(this Node node) where T : class {}
```

### Math Extensions
There are many useful math functions in Mathf but suprisingly, it was lacking a quadratic solver. Here's my implementation that gets both the negative and positive root.

``` csharp
/// Returns true if a non-complex solution exists.
public static bool QuadraticSolver(float a, float b, float c, out float x1, out float x2)
```

### Other Extensions
There are several additional extensions included but, I decided they probably weren't important enough to list here. See the cs file to check them out.

### License
[MIT License](https://choosealicense.com/licenses/mit/)
