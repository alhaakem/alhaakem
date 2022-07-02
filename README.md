package com.example.calculator;
import androidx.appcompat.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.EditText;
public class MainActivity extends AppCompatActivity {
 EditText t1;
 @Override
 protected void onCreate(Bundle savedInstanceState) {
 super.onCreate(savedInstanceState);
 setContentView(R.layout.activity_main);
 t1=(EditText)findViewById(R.id.id2);
 }
 public void onClick1(View view) {
 t1.setText(t1.getText() + "1");
 }
 public void onClick2(View view) {
 t1.setText(t1.getText() + "2");
 }
 public void onClick3(View view) {
 t1.setText(t1.getText() + "3");
 }
 public void onClick4(View view) {
 t1.setText(t1.getText() + "4");
 }
 public void onClick5(View view) {
 t1.setText(t1.getText() + "5");
 }
 public void onClick6(View view) {
 t1.setText(t1.getText() + "6");
 }
 public void onClick7(View view) {
 t1.setText(t1.getText() + "7");
 }
 public void onClick8(View view) {
 t1.setText(t1.getText() + "8");
 }
 public void onClick9(View view) {
 t1.setText(t1.getText() + "9");
 }
 public void onClick0(View view) {
 t1.setText(t1.getText() + "0");
 }
 public void onClickdot(View view) {
 int i = 0;
 boolean dot = false;
 String str = t1.getText().toString();
 while (i < str.length()) {
 if (str.charAt(i) != '.')
 i++;
 else {
 dot = true;
 break;
 }
 }
 if (!dot)
 t1.setText(t1.getText() + ".");
 }
 public void onClickc(View view) {
 t1.setText("");
 }
 public void onClickplus(View view) {
 t1.setText(t1.getText() + "+");
 }
 public void onClickminus(View view) {
 t1.setText(t1.getText() + "-");
 }
 public void onClickmulti(View view) {
 t1.setText(t1.getText() + "*");
 }
 public void onClickdiv(View view) {
 t1.setText(t1.getText() + "/");
 }
 public void onClickEqual(View view) {
 String str = t1.getText().toString();
 int p1 = 0, p2 = 0, res;
 String res1, op1 = null, op2 = null;
 try {
 if (str.contains("+")) {
 String[] oprands = str.split("\\+");
 op1 = oprands[0];
 op2 = oprands[1];
 p1 = Integer.parseInt(op1);
 p2 = Integer.parseInt(op2);
 res = p1 + p2;
 res1 = Integer.toString(res);
 t1.setText( res1+"");
 }
 if (str.contains("-")) {
 String oprands[] = str.split("-");
 op1 = oprands[0];
 op2 = oprands[1];
 p1 = Integer.parseInt(op1);
 p2 = Integer.parseInt(op2);
 res = p1 - p2;
 res1 = Integer.toString(res);
 t1.setText(res1+"");
 }
 if (str.contains("*")) {
 String oprands[] = str.split("\\*");
 op1 = oprands[0];
 op2 = oprands[1];
 p1 = Integer.parseInt(op1);
 p2 = Integer.parseInt(op2);
 res = p1 * p2;
 res1 = Integer.toString(res);
 t1.setText(res1+"");
 }
 if (str.contains("/")) {
 String oprands[] = str.split("/");
 op1 = oprands[0];
 op2 = oprands[1];
 float f1 = Float.parseFloat(op1);
 float f2 = Float.parseFloat(op2);
 float res2 = f1 / f2;
 res1 = Float.toString(res2);
 t1.setText(res1+"");
 }
 }catch(Exception e){t1.setText("Error");}
 }
}
