![Travis-ci](https://api.travis-ci.org/MLSDev/AnimatedRecyclerView.svg)

# AnimatedRecyclerView
A RecyclerView with layout animations

## Demo
<img src="art/demo.gif" width="32%">

## Setup
To use this library your `minSdkVersion` must be >= 16.

In your build.gradle :
```gradle
dependencies {
    // Kotlin
    implementation "com.mlsdev.animatedrv:library:1.0.1"
    
    // Java
    compile "com.mlsdev.animatedrv:library:1.0.1"
}
```

## Example
### From the layout
```xml
<com.mlsdev.animatedrv.AnimatedRecyclerView
        android:id="@+id/recycler_view"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        app:animationDuration="600"
        app:layoutAnimation="@anim/layout_animation_from_bottom"
        app:layoutManagerOrientation="vertical"
        app:layoutManagerReverse="false"
        app:layoutManagerType="linear" />
```
### From the code
```java
AnimatedRecyclerView recyclerView = new AnimatedRecyclerView.Builder(this)
                .orientation(LinearLayoutManager.VERTICAL)
                .layoutManagerType(AnimatedRecyclerView.LayoutManagerType.LINEAR)
                .animation(R.anim.layout_animation_from_bottom)
                .animationDuration(600)
                .reverse(false)
                .build();
```

### Start animation
- First option
```java
adapter.notifyDataSetChanged();
recyclerView.scheduleLayoutAnimation();
```
- Second option
Your `RecyclerView` must be casted to the `AnimatedRecyclerView` and an adapter must be set.
```java
recyclerView.notifyDataSetChanged();
```

## Authors
* [Sergey Petrosyuk](mailto:petrosyuk@mlsdev.com), MLSDev 

## About MLSDev

[<img src="https://cloud.githubusercontent.com/assets/1778155/11761239/ccfddf60-a0c2-11e5-8f2a-8573029ab09d.png" alt="MLSDev.com">][mlsdev]

AnimatedRecyclerView is maintained by MLSDev, Inc. We specialize in providing all-in-one solution in mobile and web development. Our team follows Lean principles and works according to agile methodologies to deliver the best results reducing the budget for development and its timeline. 

Find out more [here][mlsdev] and don't hesitate to [contact us][contact]!

[mlsdev]: http://mlsdev.com
[contact]: http://mlsdev.com/contact_us
[github-frederikos]: https://github.com/SerhiyPetrosyuk
