
# SingleChildScrollView class

A box in which a single widget can be scrolled.

This widget is useful when you have a single box that will normally be entirely visible, for example a clock face in a time picker, but you need to make sure it can be scrolled if the container gets too small in one axis (the scroll direction).

It is also useful if you need to shrink-wrap in both axes (the main scrolling direction as well as the cross axis), as one might see in a dialog or pop-up menu. In that case, you might pair the [SingleChildScrollView](https://api.flutter.dev/flutter/widgets/SingleChildScrollView-class.html) with a [ListBody](https://api.flutter.dev/flutter/widgets/ListBody-class.html) child.