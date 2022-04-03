---
layout: post
title: OutlinedTextField - Jetpack Compose
categories: [Blog, Android, Tutorial]
tags: [Blog, Android, Tutorial]
fullview: false
comments: false
---
For this tutorial, we will be looking at text fields.<br>
<br>
Text fields allow users to enter text into a UI. Text fields in Material design come in two types: Filled text fields or Outlined text fields. Outlined text fields are what we shall look at here. 

Compose includes an OutlinedTextField composable to fulfill the Material specification of outlined text field.
<br>
<h3>Lets Look at Some Code</h3> 
<br>
Here I have created a composable that shows some different variations of how OutlinedTextField could be used.
<br>
```kotlin
@Composable
fun textFields() {
    var text by remember { mutableStateOf("") }
    var textone by remember { mutableStateOf("") }
    var texttwo by remember { mutableStateOf("") }
    var password by rememberSaveable { mutableStateOf("") }

    Column(
        modifier = Modifier.fillMaxSize(),
        verticalArrangement = Arrangement.Center

    ) {Row(
        horizontalArrangement = Arrangement.Center,
        modifier = Modifier
            .fillMaxWidth()
            .height(100.dp)


    ) {
        OutlinedTextField(
            value = text,
            onValueChange = { text = it },
            singleLine = true,
            label = { Text("Label") },
            colors = TextFieldDefaults.outlinedTextFieldColors(
                focusedBorderColor = White,
                unfocusedBorderColor = White,
                focusedLabelColor = White,
                unfocusedLabelColor = White,
                textColor = White
            )
        )
    }
        Row(
            horizontalArrangement = Arrangement.Center,
            modifier = Modifier
                .fillMaxWidth()
                .height(100.dp)


        ) {
            OutlinedTextField(
                value = textone,
                onValueChange = { textone = it },
                singleLine = true,
                label = { Text("Label") },
                colors = TextFieldDefaults.outlinedTextFieldColors(
                    focusedBorderColor = Green,
                    unfocusedBorderColor = Yellow,
                    focusedLabelColor = Green,
                    unfocusedLabelColor = Yellow,
                    textColor = Green,
                ),
                shape = RoundedCornerShape(50)
            )
        }
        Row(
            horizontalArrangement = Arrangement.Center,
            modifier = Modifier
                .fillMaxWidth()
                .height(100.dp)

        ) {
            OutlinedTextField(
                value = texttwo,
                onValueChange = { texttwo = it },
                singleLine = true,
                label = { Text("Email", color = White) },
                leadingIcon = { Icon(imageVector = Icons.Default.Email,contentDescription = "", tint = White) },
                colors = TextFieldDefaults.outlinedTextFieldColors(
                    focusedBorderColor = Red,
                    unfocusedBorderColor = White,
                    textColor = White
                ),
                shape = RoundedCornerShape(50)
            )
        }

        Row(
            horizontalArrangement = Arrangement.Center,
            modifier = Modifier
                .fillMaxWidth()
                .height(100.dp)

        ) {
            OutlinedTextField(
                value = password,
                onValueChange = { password = it },
                label = { Text("Enter password") },
                leadingIcon = { Icon(imageVector = Icons.Default.Lock,contentDescription = "", tint = Red) },
                colors = TextFieldDefaults.outlinedTextFieldColors(
                    focusedBorderColor = White,
                    unfocusedBorderColor = Red,
                    focusedLabelColor = White,
                    unfocusedLabelColor = Red,
                    textColor = White,
                ),
                visualTransformation = PasswordVisualTransformation(),
                keyboardOptions = KeyboardOptions(keyboardType = KeyboardType.Password)
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
  <source src="/assets/media/compose_labels.mp4" type="video/mp4">
Your browser does not support the video tag.
</video>