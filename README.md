activity_main.xml:
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
 xmlns:app="http://schemas.android.com/apk/res-auto"
 xmlns:tools="http://schemas.android.com/tools"
 android:layout_width="match_parent"
 android:layout_height="match_parent"
 android:background="#00ACC1"
 tools:context=".MainActivity">
 <Button
 android:id="@+id/generate"
 android:layout_width="fill_parent"
 android:layout_height="wrap_content"
 android:layout_marginTop="24dp"
 android:text="Generate random number"
 app:layout_constraintBottom_toBottomOf="parent"
 app:layout_constraintHorizontal_bias="0.0"
 app:layout_constraintLeft_toLeftOf="parent"
 app:layout_constraintRight_toRightOf="parent"
 app:layout_constraintTop_toTopOf="parent"
 app:layout_constraintVertical_bias="0.0" />
 <TextView
 android:id="@+id/generatenumber"
 android:layout_width="wrap_content"
 android:layout_height="130dp"
 android:maxLines="1"
 android:textAlignment="center"
 android:textColor="#D81B60"
 android:textSize="60sp"
 app:autoSizeTextType="uniform"
 app:layout_constraintBottom_toBottomOf="parent"
 app:layout_constraintLeft_toLeftOf="parent"
 app:layout_constraintRight_toRightOf="parent"
 app:layout_constraintTop_toTopOf="parent" />
</androidx.constraintlayout.widget.ConstraintLayout>
MainActivity.java:
package com.example.randomnumber;
import androidx.appcompat.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.TextView;
import java.util.Random;
public class MainActivity extends AppCompatActivity {
 @Override
 protected void onCreate(Bundle savedInstanceState) {
 super.onCreate(savedInstanceState);
 setContentView(R.layout.activity_main);
 final Random myRandom = new Random();
 Button buttonGenerate = (Button)findViewById(R.id.generate);
 final TextView textGenerateNumber = (TextView)findViewById(R.id.generatenumber);
 buttonGenerate.setOnClickListener(new View.OnClickListener(){
 @Override
 public void onClick(View v) {
 // TODO Auto-generated method stub
 textGenerateNumber.setText(String.valueOf(myRandom.nextInt(100)));
 }
 });
 }
}
