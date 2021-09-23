---
title: Save and Restore ScrollView and RecyclerView Scroll Position in Android
date: 2018-06-21 00:00:00 Z
tags:
- Android
---

There are lots of suggestions in the internet on how to save & restore scroll position in android scrollable view, from saving the scroll *(x, y)* position in `onSaveInstanceState(Bundle outState)` then restore it in `onRestoreInstanceState(Bundle savedInstanceState)` and even creating a child class of `ScrollView` to do this saving & restoring tasks, etc.

Actually it much simpler than I thought, we don't need to do anything else to have the same behaviour, the framework (`ScrollView` and `RecyclerView`) has done the job for us.

<!--more-->

Here what you need to do:
- You need to set an **ID** attribute for any scrollable view such as `ScrollView`.
- Provide data to the `RecyclerView` in the first layout pass *(syncronously)*, so you need to cache the data and restore it right away when there is configuration changes.

...and that's it.

## References

[https://stackoverflow.com/questions/29208086/save-the-position-of-scrollview-when-the-orientation-changes](https://stackoverflow.com/questions/29208086/save-the-position-of-scrollview-when-the-orientation-changes)

[https://medium.com/@dimezis/android-scroll-position-restoring-done-right-cff1e2104ac7](https://medium.com/@dimezis/android-scroll-position-restoring-done-right-cff1e2104ac7)