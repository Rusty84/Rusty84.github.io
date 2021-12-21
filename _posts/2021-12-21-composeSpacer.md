---
layout: post
title: Spacer - Jetpack Compose
categories: [Blog, Android, Tutorial]
tags: [Blog, Android, Tutorial]
fullview: false
comments: false
---
The last post from me of 2021. I have been delving deeper into Android Jetpack Compose and wanted to create some tutorial posts.
<br>
<br>
For this tutorial, we will be looking at the Spacer component.

<h3>What is Spacer?</h3> 
<br>
The Spacer component is used to display an empty space. Width and (or) height can be set for Spacer using Modifier object.
<br>
```kotlin
@Composable
fun Spacer() {
    Column(
        modifier = Modifier.fillMaxSize(),
        verticalArrangement = Arrangement.Center
    ) {
        Row(
            modifier = Modifier
                .fillMaxWidth()
                .height(100.dp)
        ) {
            Box(
                modifier = Modifier
                    .fillMaxHeight()
                    .weight(1f)
                    .background(Color.Green)
            )
        }
    }
}
```
Here I have created a composable that shows a green box. Contained in a column and row.
<br>
<br>
<br>
<video style="display:block; margin: 0 auto;" controls="controls" autoplay = "autoplay" loop="loop" width="300" height="500">
  <source src="/assets/media/spacer_green.mp4" type="video/mp4">
Your browser does not support the video tag.
</video>
<br>
<br>
Let's see what happens when we add another box to the composable.
<br>
```kotlin
@Composable
fun Spacer() {
    Column(
        modifier = Modifier.fillMaxSize(),
        verticalArrangement = Arrangement.Center
    ) {
        Row(
            modifier = Modifier
                .fillMaxWidth()
                .height(100.dp)
        ) {
            Box(
                modifier = Modifier
                    .fillMaxHeight()
                    .weight(1f)
                    .background(Color.Green)
            )

            Box(
                modifier = Modifier
                    .fillMaxHeight()
                    .weight(1f)
                    .background(Color.Red)
            )
        }
    }
}
```
Awesome. We now have a Green and Red box displaying on our screen.
<br>
<br>
<br>
<video style="display:block; margin: 0 auto;" controls="controls" autoplay = "autoplay" loop="loop" width="300" height="500">
  <source src="/assets/media/spacer_red.mp4" type="video/mp4">
Your browser does not support the video tag.
</video>
<br>
<br>
It looks good but not quite what we want. Let's use Spacer to create a gap between the green and red boxes.
<br>
```kotlin
@Composable
fun Spacer() {
    Column(
        modifier = Modifier.fillMaxSize(),
        verticalArrangement = Arrangement.Center
    ) {
        Row(
            modifier = Modifier
                .fillMaxWidth()
                .height(100.dp)
        ) {
            Box(
                modifier = Modifier
                    .fillMaxHeight()
                    .weight(1f)
                    .background(Color.Green)
            )
            Spacer(modifier = Modifier.width(50.dp))
            Box(
                modifier = Modifier
                    .fillMaxHeight()
                    .weight(1f)
                    .background(Color.Red)
            )
        }
    }
}
```
Adding the Spacer component has given us a nice gap between the green and red boxes.
<br>
<br>
<h3>Let's See It in Action</h3> 
<br>
<br>
<video style="display:block; margin: 0 auto;" controls="controls" autoplay = "autoplay" loop="loop" width="300" height="500">
  <source src="/assets/media/box_spacer.mp4" type="video/mp4">
Your browser does not support the video tag.
</video>