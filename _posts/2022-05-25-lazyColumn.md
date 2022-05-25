---
layout: post
title: LazyColumn - Jetpack Compose
categories: [Blog, Android, Tutorial]
tags: [Blog, Android, Tutorial]
fullview: false
comments: false
---
For this tutorial, we will be looking at creating a scrollable list inside a LazyColumn<br>
<br>
If we wanted to display a large number of items or a list of an unknown length. Using a layout such as Column can cause performance issues, as all the items will be composed and laid out whether or not they are visible. 

Jetpack Compose provides a set of components which only compose and lay out items which are visible in the component’s viewport. These components include LazyColumn. 
<br>
<h3>Lets Look at Some Code</h3> 
<br>
Here I have created a composable that shows some different variations of how OutlinedTextField could be used.
<br>
```kotlin
@Composable
fun scrollList() {
    LazyColumn (
        modifier = Modifier
            .fillMaxSize()
            .background(colorResource(id = R.color.black))
            .wrapContentSize(Alignment.Center))
    {
        items(100) {
            Text(
                text = "Item $it",
                fontWeight = FontWeight.Bold,
                color = Color.White,
                textAlign = TextAlign.Center,
                fontSize = 25.sp,
                modifier = Modifier
                    .fillParentMaxWidth()
                    .padding(vertical = 24.dp),
            )
        }
    }
}
```
<br>
<br>
<h3>Let's See It in Action</h3> 
<br>
<br>
<video style="display:block; margin: 0 auto;" controls="controls" autoplay = "autoplay" loop="loop" width="300" height="500">
  <source src="/assets/media/lc_list.mp4" type="video/mp4">
Your browser does not support the video tag.
</video>