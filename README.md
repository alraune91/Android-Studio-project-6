Screenshot_4.png
package com.example.as_lesson_5;

import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;
import android.text.TextUtils;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.TextView;

public class MainActivity extends AppCompatActivity {
    EditText etNum1;
    EditText etNum2;
    Button btnDel;
    Button btnUmn;
    Button btnMin;
    Button btnPlus;
    TextView tvResult;
    String oper = "";


    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        etNum1 = findViewById(R.id.et1);
        etNum2 = findViewById(R.id.et2);
        btnDel = findViewById(R.id.button1);
        btnUmn = findViewById(R.id.button2);
        btnMin = findViewById(R.id.button3);
        btnPlus = findViewById(R.id.button4);
        tvResult = findViewById(R.id.textView);
    }
    public void onClick(View v){
        float num1 = 0;
        float num2 = 0;
        float result = 0;
        if (TextUtils.isEmpty(etNum1.getText().toString())
                || TextUtils.isEmpty((etNum2.getText().toString()))){
            return;
        }
        num1 = Float.parseFloat(etNum1.getText().toString());
        num2 = Float.parseFloat(etNum2.getText().toString());
        int id = v.getId();
        if (id == R.id.button4) {
            oper = "+";
            result = num1 + num2;
        } else if (id == R.id.button3) {
            oper = "-";
            result = num1 - num2;
        }
        else if (id == R.id.button2) {
            oper = "*";
            result = num1 * num2;
        } else if (id == R.id.button1) {
            oper = "/";
            result = num1 / num2;
        }
        tvResult.setText(num1 + " "+ oper + " " + num2 + "=" + result);
    }
}
