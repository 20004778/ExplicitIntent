# ExplicitIntent

Develop program to create two screens , first screen will take one number input from user. After click on Factorial button, second screen will open and it should display factorial of the same number using Explicit Intents.

## AIM:

To display factorial number using Explicit Intents in Android Studio.

## EQUIPMENTS REQUIRED:

Android Studio(Min. required Artic Fox)

## ALGORITHM:

## Step 1:
Open Android Stdio and then click on File -> New -> New project.

## Step 2:
Then type the Application name as “ex.no.2″ and click Next. 

## Step 3:
Then select the Minimum SDK as shown below and click Next.

## Step 4:
Then select the Empty Activity and click Next. Finally click Finish.

## Step 5: 
Design layout in activity_main.xml.

## Step 6:
open google page using Implicit Intents and display factorial number using Explicit Intents in MainActivity file.

## Step 7:
Save and run the application.

## PROGRAM:

```java
Developed by: SURYA R
Registeration Number : 212220230052

```
#### MainActivity.java
```java
package com.example.impliciteexplicite;

import androidx.appcompat.app.AppCompatActivity;

import android.content.Intent;
import android.os.Bundle;
import android.view.View;
import android.widget.EditText;

public class MainActivity extends AppCompatActivity {
    EditText etNumber;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        etNumber=findViewById(R.id.etNumber);
    }
    public void displayFactorial(View view){
        Intent i=new Intent(MainActivity.this,MainActivity2.class);
        i.putExtra("number",etNumber.getText().toString());
        startActivity(i);
    }
}
```
#### activity_main.xml
```java
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity"
    android:orientation="vertical"
    android:padding="20dp">

    <EditText android:id="@+id/etNumber"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="@string/enter_the_number"
        android:inputType="number"
        android:layout_marginTop="50dp"
        android:importantForAutofill="no" />

    <Button
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="@string/factorial"
        android:onClick="displayFactorial"/>

</LinearLayout>
```
#### MainActivity2.java
```java
package com.example.impliciteexplicite;

import androidx.appcompat.app.AppCompatActivity;

import android.annotation.SuppressLint;
import android.os.Bundle;
import android.widget.TextView;

public class MainActivity2 extends AppCompatActivity {
    TextView tv;

    @SuppressLint("SetTextI18n")
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main2);
        Bundle b=getIntent().getExtras();
        int no=Integer.parseInt(b.getString("number"));
        long f=1;
        for(int i=no;i>0;i--)
        {
            f=f*i;
        }
        tv=findViewById(R.id.tv);
        tv.setText("Factorial of "+no+" is "+f);
    }
}
```
#### activity_main2.xml
```java
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity2"
    android:padding="20dp">

    <TextView android:id="@+id/tv"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:text="@string/factorial_of_number_is"
        style="@style/TextAppearance.AppCompat.Large"/>

</RelativeLayout>
```

## OUTPUT:
![Screenshot (268)](https://user-images.githubusercontent.com/75236145/165446706-14f5ca87-83a0-499c-af5c-172293cc9ce3.png)

![Screenshot (269)](https://user-images.githubusercontent.com/75236145/165446714-12dcaf76-9cb9-4d55-9b87-e409f31507db.png)


## RESULT:

Thus a Simple Explicit Intents using Android Studio is developed and executed successfully.
