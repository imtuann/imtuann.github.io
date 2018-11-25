---
layout: post
title: Floating Action Button Expandable like Messages app on the Pixel devices
---

An android library that brings the float action button expandable. You can include optional contents and use everywhere.

## Preview

![FloatingActionButtonExpandable][FloatingActionButtonExpandable]

## Usage

### Code

```kotlin
val fab = findViewById<FloatActionButtonExpandable>(R.id.fab)
recyclerView.addOnScrollListener(object : RecyclerView.OnScrollListener() {
    override fun onScrolled(recyclerView: RecyclerView, dx: Int, dy: Int) {
        if (dy > 0) {
            fab.collapse()
        } else {
            fab.expand()
        }
    }
})
// toggle expand, collapse
fab.toggle()
// expand
fab.expand()
// collapse
fab.collapse()

fab.setExpanded(true)
fab.setDuration(100L)
fab.setContent("Start Chat")
// drawable, resId, bitmap
fab.setIconActionButton(R.drawable.ic_message_white_24dp)
fab.setTextColor(ContextCompat.getColor(this, android.R.color.white))
fab.setBackgroundButtonColor(ContextCompat.getColor(this, R.color.bg_float_action))
// padding between the icon and text
fab.setPaddingTextIcon(resources.getDimensionPixelSize(R.dimen.padding_text_icon))
// padding inside the button
fab.setPaddingInsideButton(resources.getDimensionPixelSize(R.dimen.padding_fab))
// pixel
fab.setTextSize(resources.getDimensionPixelSize(R.dimen.text_size_fab).toFloat())
// or
fab.setTextSize(TypedValue.COMPLEX_UNIT_SP, 14)
```

### Layout xml

add `xmlns:app="http://schemas.android.com/apk/res-auto"`

```xml
<com.tuann.floatingactionbuttonexpandable.FloatingActionButtonExpandable
    android:id="@+id/fab"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    app:fab_content="@string/label_start_chat"
    app:fab_padding_text_icon="@dimen/padding_text_icon"
    app:fab_text_color="@android:color/white"
    app:fab_bg_color="@color/bg_float_action"
    app:fab_icon="@drawable/ic_message_white_24dp"
    app:fab_duration="100"
    app:fab_text_size="@dimen/text_size_action_button"
    app:fab_padding="@dimen/padding_fab"
    app:fab_expanded="true"/>
```

## Attributes

|attribute name|description|
|:-:|:-:|
|fab_content|The content of the button|
|fab_padding_text_icon|The padding between the text and icon|
|fab_text_color|The color of the text|
|fab_bg_color|The background color of the button|
|fab_icon|The icon of the button|
|fab_duration|The length of the expand or collapse animation|
|fab_text_size|The text size of the button|
|fab_padding|The padding inside the button|
|fab_expanded|The button is expanded if you set true|

## Setup

[![](https://jitpack.io/v/imtuann/FloatingActionButtonExpandable.svg)](https://jitpack.io/#imtuann/FloatingActionButtonExpandable)

Step 1. Add the JitPack repository in your root build.gradle at the end of repositories:
```
allprojects {
    repositories {
        ...
        maven { url 'https://jitpack.io' }
    }
}
```

Step 2. Add the dependency
```
implementation 'com.github.imtuann:FloatingActionButtonExpandable:1.0.3'
```

## Source code
You can find this project on [my github page](https://github.com/imtuann/FloatingActionButtonExpandable)

[FloatingActionButtonExpandable]: /gifs/FloatingActionButtonExpandable.gif