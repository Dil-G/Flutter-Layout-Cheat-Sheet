# Flutter-Layout-Cheat-Sheet
This repo includes identified Flutter Layouts which anyone can refer as their layout cheat sheet.

# Widget catalog


## Accessibility widgets

## 1.ExcludeSemantics  class

A widget that drops all the semantics of its descendants.

## Properties

[excluding](https://api.flutter.dev/flutter/widgets/ExcludeSemantics/excluding.html)  →  [bool](https://api.flutter.dev/flutter/dart-core/bool-class.html)

Whether this widget is excluded in the semantics tree.

[child](https://api.flutter.dev/flutter/widgets/SingleChildRenderObjectWidget/child.html)  →  [Widget](https://api.flutter.dev/flutter/widgets/Widget-class.html)

The widget below this widget in the tree.  [[...]](https://api.flutter.dev/flutter/widgets/SingleChildRenderObjectWidget/child.html)

[hashCode](https://api.flutter.dev/flutter/dart-core/Object/hashCode.html)  →  [int](https://api.flutter.dev/flutter/dart-core/int-class.html)

The hash code for this object.  [[...]](https://api.flutter.dev/flutter/dart-core/Object/hashCode.html)

[key](https://api.flutter.dev/flutter/widgets/Widget/key.html)  →  [Key](https://api.flutter.dev/flutter/foundation/Key-class.html)

Controls how one widget replaces another widget in the tree.  [[...]](https://api.flutter.dev/flutter/widgets/Widget/key.html)

[runtimeType](https://api.flutter.dev/flutter/dart-core/Object/runtimeType.html)  →  [Type](https://api.flutter.dev/flutter/dart-core/Type-class.html)

A representation of the runtime type of the object.


## Operators

[operator ==](https://api.flutter.dev/flutter/dart-core/Object/operator_equals.html)(dynamic  other)  →  [bool](https://api.flutter.dev/flutter/dart-core/bool-class.html)

The equality operator.  [[...]](https://api.flutter.dev/flutter/dart-core/Object/operator_equals.html)

## 2.MergeSemantics  class

A widget that merges the semantics of its descendants

## Properties

[child](https://api.flutter.dev/flutter/widgets/SingleChildRenderObjectWidget/child.html)  →  [Widget](https://api.flutter.dev/flutter/widgets/Widget-class.html)

The widget below this widget in the tree.  [[...]](https://api.flutter.dev/flutter/widgets/SingleChildRenderObjectWidget/child.html)

[hashCode](https://api.flutter.dev/flutter/dart-core/Object/hashCode.html)  →  [int](https://api.flutter.dev/flutter/dart-core/int-class.html)

The hash code for this object.  [[...]](https://api.flutter.dev/flutter/dart-core/Object/hashCode.html)

[key](https://api.flutter.dev/flutter/widgets/Widget/key.html)  →  [Key](https://api.flutter.dev/flutter/foundation/Key-class.html)

Controls how one widget replaces another widget in the tree.  [[...]](https://api.flutter.dev/flutter/widgets/Widget/key.html)

[runtimeType](https://api.flutter.dev/flutter/dart-core/Object/runtimeType.html)  →  [Type](https://api.flutter.dev/flutter/dart-core/Type-class.html)

A representation of the runtime type of the object.

## Operators

[operator ==](https://api.flutter.dev/flutter/dart-core/Object/operator_equals.html)(dynamic  other)  →  [bool](https://api.flutter.dev/flutter/dart-core/bool-class.html)

The equality operator.  [[...]](https://api.flutter.dev/flutter/dart-core/Object/operator_equals.html)
# Scrolling widgets

## 1.CustomScrollView  class

A  [ScrollView](https://api.flutter.dev/flutter/widgets/ScrollView-class.html)  that creates custom scroll effects using slivers.

This sample code shows a scroll view that contains a flexible pinned app bar, a grid, and an infinite list.


```dart
CustomScrollView(
  slivers: <Widget>[
    const SliverAppBar(
      pinned: true,
      expandedHeight: 250.0,
      flexibleSpace: FlexibleSpaceBar(
        title: Text('Demo'),
      ),
    ),
    SliverGrid(
      gridDelegate: SliverGridDelegateWithMaxCrossAxisExtent(
        maxCrossAxisExtent: 200.0,
        mainAxisSpacing: 10.0,
        crossAxisSpacing: 10.0,
        childAspectRatio: 4.0,
      ),
      delegate: SliverChildBuilderDelegate(
        (BuildContext context, int index) {
          return Container(
            alignment: Alignment.center,
            color: Colors.teal[100 * (index % 9)],
            child: Text('Grid Item $index'),
          );
```
### Accessibility
A [CustomScrollView](https://api.flutter.dev/flutter/widgets/CustomScrollView-class.html) can allow Talkback/VoiceOver to make announcements to the user when the scroll state changes.

## 2.GridView  class
A scrollable, 2D array of widgets.
The main axis direction of a grid is the direction in which it scrolls (the [scrollDirection](https://api.flutter.dev/flutter/widgets/ScrollView/scrollDirection.html)).

### Transitioning to  [CustomScrollView](https://api.flutter.dev/flutter/widgets/CustomScrollView-class.html)

A  [GridView](https://api.flutter.dev/flutter/widgets/GridView-class.html)  is basically a  [CustomScrollView](https://api.flutter.dev/flutter/widgets/CustomScrollView-class.html)  with a single  [SliverGrid](https://api.flutter.dev/flutter/widgets/SliverGrid-class.html)  in its  [CustomScrollView.slivers](https://api.flutter.dev/flutter/widgets/CustomScrollView/slivers.html)  property.

If  [GridView](https://api.flutter.dev/flutter/widgets/GridView-class.html)  is no longer sufficient, for example because the scroll view is to have both a grid and a list, or because the grid is to be combined with a  [SliverAppBar](https://api.flutter.dev/flutter/material/SliverAppBar-class.html), etc, it is straight-forward to port code from using  [GridView](https://api.flutter.dev/flutter/widgets/GridView-class.html)  to using  [CustomScrollView](https://api.flutter.dev/flutter/widgets/CustomScrollView-class.html)  directly

Sample

This example demonstrates how to create a  [GridView](https://api.flutter.dev/flutter/widgets/GridView-class.html)  with two columns. The children are spaced apart using the  `crossAxisSpacing`  and  `mainAxisSpacing`  properties.

![A screenshot of a GridView](https://flutter.github.io/assets-for-api-docs/assets/widgets/grid_view.png)

_assignment_

```dart
GridView.count(
  primary: false,
  padding: const EdgeInsets.all(20),
  crossAxisSpacing: 10,
  mainAxisSpacing: 10,
  crossAxisCount: 2,
  children: <Widget>[
    Container(
      padding: const EdgeInsets.all(8),
      child: const Text('He\'d have you all unravel at the'),
      color: Colors.teal[100],
    ),
    Container(
      padding: const EdgeInsets.all(8),
      child: const Text('Heed not the rabble'),
      color: Colors.teal[200],
    ),
    Container(
      padding: const EdgeInsets.all(8),
      child: const Text('Sound of screams but the'),
      color: Colors.teal[300],
    ),
    Container(
      padding: const EdgeInsets.all(8),
      child: const Text('Who scream'),
      color: Colors.teal[400],
    ),
    Container(
      padding: const EdgeInsets.all(8),
      child: const Text('Revolution is coming...'),
      color: Colors.teal[500],
    ),
    Container(
      padding: const EdgeInsets.all(8),
      child: const Text('Revolution, they...'),
      color: Colors.teal[600],
    ),
  ],
)
```


Sample

This example shows how to create the same grid as the previous example using a  [CustomScrollView](https://api.flutter.dev/flutter/widgets/CustomScrollView-class.html)  and a  [SliverGrid](https://api.flutter.dev/flutter/widgets/SliverGrid-class.html).

![A screenshot of a CustomScrollView with a SliverGrid](https://flutter.github.io/assets-for-api-docs/assets/widgets/grid_view_custom_scroll.png)


```dart
CustomScrollView(
  primary: false,
  slivers: <Widget>[
    SliverPadding(
      padding: const EdgeInsets.all(20),
      sliver: SliverGrid.count(
        crossAxisSpacing: 10,
        mainAxisSpacing: 10,
        crossAxisCount: 2,
        children: <Widget>[
          Container(
            padding: const EdgeInsets.all(8),
            child: const Text('He\'d have you all unravel at the'),
            color: Colors.green[100],
          ),
          Container(
            padding: const EdgeInsets.all(8),
            child: const Text('Heed not the rabble'),
            color: Colors.green[200],
          ),
          Container(
            padding: const EdgeInsets.all(8),
            child: const Text('Sound of screams but the'),
            color: Colors.green[300],
```

## 3.ListView  class

A scrollable list of widgets arranged linearly.
Sample

This example uses the default constructor for  [ListView](https://api.flutter.dev/flutter/widgets/ListView-class.html)  which takes an explicit  [List<Widget>](https://api.flutter.dev/flutter/dart-core/List-class.html)  of children. This  [ListView](https://api.flutter.dev/flutter/widgets/ListView-class.html)'s children are made up of  [Container](https://api.flutter.dev/flutter/widgets/Container-class.html)s with  [Text](https://api.flutter.dev/flutter/widgets/Text-class.html).

![A ListView of 3 amber colored containers with sample text.](https://flutter.github.io/assets-for-api-docs/assets/widgets/list_view.png)


```dart
ListView(
  padding: const EdgeInsets.all(8),
  children: <Widget>[
    Container(
      height: 50,
      color: Colors.amber[600],
      child: const Center(child: Text('Entry A')),
    ),
    Container(
      height: 50,
      color: Colors.amber[500],
      child: const Center(child: Text('Entry B')),
    ),
    Container(
      height: 50,
      color: Colors.amber[100],
      child: const Center(child: Text('Entry C')),
    ),
  ],
)
```