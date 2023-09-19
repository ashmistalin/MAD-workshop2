# MAD-workshop2

## Create a simple application for division of two number using explicit intent in android studio.

## AIM:
To Create a simple application for division of two number using explicit intent in android studio.

## PROGRAM:
```
/*
Submitted by: ASHMI S
Register number: 212221040021
*/
```
## activity_main.xml:
```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
xmlns:app="http://schemas.android.com/apk/res-auto" xmlns:tools="http://schemas.android.com/tools" android:layout_width="match_parent" android:layout_height="match_parent" tools:context=".MainActivity">

<EditText android:id="@+id/num1"
android:layout_width="wrap_content" android:layout_height="wrap_content" android:ems="10" android:inputType="textPersonName" android:text="Operand 1" app:layout_constraintBottom_toTopOf="@+id/num2" app:layout_constraintEnd_toEndOf="parent" app:layout_constraintHorizontal_bias="0.497" app:layout_constraintStart_toStartOf="parent" app:layout_constraintTop_toTopOf="parent" app:layout_constraintVertical_bias="0.813" />
 
<EditText android:id="@+id/num2"
android:layout_width="wrap_content" android:layout_height="wrap_content" android:layout_marginBottom="100dp" android:ems="10" android:inputType="textPersonName" android:text="Operand 2" app:layout_constraintBottom_toTopOf="@+id/div" app:layout_constraintEnd_toEndOf="parent" app:layout_constraintHorizontal_bias="0.497" app:layout_constraintStart_toStartOf="parent" />

<Button
android:id="@+id/div" android:layout_width="wrap_content" android:layout_height="wrap_content" android:layout_marginBottom="244dp" android:text="DIVIDE" app:layout_constraintBottom_toBottomOf="parent" app:layout_constraintEnd_toEndOf="parent" app:layout_constraintHorizontal_bias="0.498" app:layout_constraintStart_toStartOf="parent" />

<TextView android:id="@+id/title"
android:layout_width="wrap_content" android:layout_height="wrap_content" android:text="Division of Two Numbers" android:textColor="@color/Navy" android:textSize="25sp" app:fontFamily="sans-serif-condensed"
app:layout_constraintBottom_toTopOf="@+id/num1" app:layout_constraintEnd_toEndOf="parent" app:layout_constraintHorizontal_bias="0.496" app:layout_constraintStart_toStartOf="parent"
 
app:layout_constraintTop_toTopOf="parent" />
</androidx.constraintlayout.widget.ConstraintLayout>

```

## MainActivity.java:
```
package com.example.workshop2; import
androidx.appcompat.app.AppCompatActivity; import


android.content.Intent; import android.os.Bundle; import android.view.View; import android.widget.Button; import android.widget.EditText;

public class MainActivity extends AppCompatActivity {


EditText x; EditText y; Button btn;

@Override
protected void onCreate(Bundle savedInstanceState) { super.onCreate(savedInstanceState); setContentView(R.layout.activity_main);

x=findViewById(R.id.num1); y=findViewById(R.id.num2); btn=findViewById(R.id.div); btn.setOnClickListener(new View.OnClickListener() {
@Override
public void onClick(View view) {
int number1=Integer.parseInt(x.getText().toString()); int number2=Integer.parseInt(y.getText().toString()); int result=number1/number2;
 
Intent i = new Intent(getApplicationContext(),MainActivity2.class); i.putExtra("key",result);
 
startActivity(i);
}
});
}
}

```

## activity_main2.xml:
```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android" xmlns:app="http://schemas.android.com/apk/res-auto" mlns:tools="http://schemas.android.com/tools" android:layout_width="match_parent" android:layout_height="match_parent" tools:context=".MainActivity2">

<TextView android:id="@+id/textView"
android:layout_width="wrap_content" android:layout_height="wrap_content" android:text="Result" android:textColor="@color/black" android:textSize="25sp"
app:fontFamily="sans-serif-condensed-medium" app:layout_constraintBottom_toTopOf="@+id/output" app:layout_constraintEnd_toEndOf="parent" app:layout_constraintStart_toStartOf="parent" app:layout_constraintTop_toTopOf="parent" />

<TextView android:id="@+id/output"
android:layout_width="wrap_content" android:layout_height="wrap_content" android:layout_marginBottom="423dp" android:text="TextView" android:textColor="@color/DarkGoldenrod" android:textSize="25sp" app:fontFamily="sans-serif-medium"
app:layout_constraintBottom_toBottomOf="parent"
 
app:layout_constraintEnd_toEndOf="parent" app:layout_constraintStart_toStartOf="parent" />
</androidx.constraintlayout.widget.ConstraintLayout>

```

## MainActivity2.java:
```
package com.example.workshop2; import
androidx.appcompat.app.AppCompatActivity; import


android.content.Intent; import android.os.Bundle; import android.widget.TextView;

public class MainActivity2 extends AppCompatActivity {


TextView soln; @Override
protected void onCreate(Bundle savedInstanceState) { super.onCreate(savedInstanceState); setContentView(R.layout.activity_main2);

soln=findViewById(R.id.output);


Intent i = getIntent();
int opt=i.getIntExtra("key",0); soln.setText(Integer.toString(opt));
}
}

```
