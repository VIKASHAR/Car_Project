## AIM:

To create an android app that displays the car name and image using Android Studio.

## EQUIPMENTS REQUIRED:

Latest Version Android Studio

## ALGORITHM:

Step 1: Open Android Stdio and then click on File -> New -> New project.

Step 2: Then type the Application name as ImplicitIntent and click Next.

Step 3: Then select the Minimum SDK as shown below and click Next.

Step 4: Then select the Empty Activity and click Next. Finally click Finish.

Step 5: Design layout in activity_main.xml.

Step 6: Display message give in MainActivity file.

Step 7: Save and run the application.


## PROGRAM:
```
/*
Program to displays the car name and image
Developed by: Vikash.A.R
Registeration Number : 212222040179
*/
```

## In activity_main.xml

   <?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <androidx.recyclerview.widget.RecyclerView
        android:id="@+id/recyclerView"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:padding="10dp"/>

</RelativeLayout>


## In MainActivity.java

   package com.example.car_project;

    import android.os.Bundle;
    import androidx.appcompat.app.AppCompatActivity;
    import androidx.recyclerview.widget.LinearLayoutManager;
    import androidx.recyclerview.widget.RecyclerView;
    
    public class MainActivity extends AppCompatActivity {
    
        private Integer[] mImageIds = {
                R.drawable.image1,
                R.drawable.image2,
                R.drawable.image3,
                R.drawable.image4,
                R.drawable.image5
        };
    
        private String[] mImageNames = {
                "Land Rover Defender",
                "Land Rover Discovery",
                "BMW M5 Competition",
                "BMW XM",
                "Audi R8"
        };
    
        @Override
        protected void onCreate(Bundle savedInstanceState) {
            super.onCreate(savedInstanceState);
            setContentView(R.layout.activity_main);
    
            RecyclerView recyclerView = findViewById(R.id.recyclerView);
            recyclerView.setLayoutManager(new LinearLayoutManager(this, LinearLayoutManager.HORIZONTAL, false));
            recyclerView.setAdapter(new ImageAdapter(this, mImageIds, mImageNames));
        }
    }

## In gallery_item.xml

<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:orientation="vertical"
    android:gravity="center">

    <ImageView
        android:id="@+id/imageView"
        android:layout_width="300dp"
        android:layout_height="350dp"
        android:scaleType="center" />

    <TextView
        android:id="@+id/textView"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="5dp"
        android:textSize="30sp"
        android:textStyle="bold"
        android:textColor="#000000"/>

</LinearLayout>

## In ImageAdapter.java

    package com.example.car_project;
    
    import android.content.Context;
    import android.view.LayoutInflater;
    import android.view.View;
    import android.view.ViewGroup;
    import android.widget.ImageView;
    import android.widget.TextView;
    import androidx.annotation.NonNull;
    import androidx.recyclerview.widget.RecyclerView;
    
    public class ImageAdapter extends RecyclerView.Adapter<ImageAdapter.ViewHolder> {
        private Context mContext;
        private Integer[] mImageIds;
        private String[] mImageNames;
        
    
        public ImageAdapter(Context context, Integer[] imageIds, String[] imageNames) {
            mContext = context;
            mImageIds = imageIds;
            mImageNames = imageNames;
        }
    
        @NonNull
        @Override
        public ViewHolder onCreateViewHolder(@NonNull ViewGroup parent, int viewType) {
            View view = LayoutInflater.from(parent.getContext()).inflate(R.layout.gallery_item, parent, false);
            return new ViewHolder(view);
        }
    
        @Override
        public void onBindViewHolder(@NonNull ViewHolder holder, int position) {
            holder.imageView.setImageResource(mImageIds[position]);
            holder.textView.setText(mImageNames[position]);
        }
    
        @Override
        public int getItemCount() {
            return mImageIds.length;
        }
    
        public static class ViewHolder extends RecyclerView.ViewHolder {
            ImageView imageView;
            TextView textView;
    
            public ViewHolder(@NonNull View itemView) {
                super(itemView);
                imageView = itemView.findViewById(R.id.imageView);
                textView = itemView.findViewById(R.id.textView);
            }
        }
    }


## OUTPUT

![IMG-20240513-WA0013](https://github.com/VIKASHAR/Car_Project/assets/119405655/5fb0705b-bd3d-4f19-9f2b-fbcfc7bbe297)
![IMG-20240513-WA0014](https://github.com/VIKASHAR/Car_Project/assets/119405655/67129ea3-7f83-429e-8e2a-faf2550d5015)
![IMG-20240513-WA0015](https://github.com/VIKASHAR/Car_Project/assets/119405655/3d8197d0-c3d1-4efc-9c35-7080909ea318)
![IMG-20240513-WA0016](https://github.com/VIKASHAR/Car_Project/assets/119405655/acfc6ee3-bf2a-4f10-9f16-929fc30f9979)

## RESULT
Thus a Simple Android Application to displays the car name and image using Android Studio is developed and executed successfully.
