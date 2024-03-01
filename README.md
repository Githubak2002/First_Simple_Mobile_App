My first simple mobile app. --- 3D image change

======================================== Activity.java file ========================================
package com.eg.try_animation;

import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;
import android.view.View;
import android.widget.ImageView;

public class MainActivity extends AppCompatActivity {

    ImageView a1,a2;
    boolean flag = false;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);

        setContentView(R.layout.activity_main);
        a1 = (ImageView)findViewById(R.id.imga);
        a2 = (ImageView)findViewById(R.id.imgb);


    }
    public void fade1(View v){
//        a1.animate().alpha(0).setDuration(1000);
         a1.animate().scaleX(.5f).scaleY(.5f).setDuration(1000);
         if(!flag){
             flag = true;
             a1.animate().scaleX(1).scaleY(1).setDuration(1000);
             a1.animate().translationX(-1000).setDuration(1000);

         }
        else{
            flag = false;
            a1.animate().scaleX(.5f).scaleY(.5f).setDuration(1000);
            a1.animate().translationX(0).setDuration(1000);

         }
    }
    public void fade(View v){
        if(!flag){
        a1.animate().alpha(0).scaleX(.5f).scaleY(.5f).setDuration(1000);
        a2.animate().alpha(1).scaleX(1).scaleY(1).setDuration(1000);
        flag = true;
        }
        else{
        a2.animate().alpha(0).scaleX(.5f).scaleY(.5f).setDuration(1000);
        a1.animate().alpha(1).scaleX(1).scaleY(1).setDuration(1000);
            flag = false;

        }
    }
}


================================== .xml file ==============================

