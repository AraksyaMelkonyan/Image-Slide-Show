package com.example.imageslideshow;

import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.view.animation.Animation;
import android.view.animation.AnimationUtils;
import android.widget.Button;
import android.widget.ImageView;

import java.util.ArrayList;

public class MainActivity extends AppCompatActivity implements View.OnClickListener {
    private ImageView imageView;
    private Button button;
    Animation animation;
    Animation butAnimation;
    private int image;

    int[] images={R.drawable.bcg, R.drawable.i, R.drawable.image1,R.drawable.image2,R.drawable.image3,R.drawable.image4, R.drawable.image5,R.drawable.image6, R.drawable.image7, R.drawable.image8, R.drawable.image9, R.drawable.image10, R.drawable.image11, R.drawable.image14};

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        imageView =(ImageView)findViewById(R.id.imageView);
        button=(Button)findViewById(R.id.button);
        button.setOnClickListener(this);
        animation = AnimationUtils.loadAnimation(this, R.anim.anim);
        butAnimation = AnimationUtils.loadAnimation(this,R.anim.butanim);


    }

    @Override
    public void onClick(View v) {
        image++;
        //image=image % images.length;
        imageView.startAnimation(animation);
        imageView.setImageResource(images[image]);
        button.startAnimation(butAnimation);

    }
}
