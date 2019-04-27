# PlaceholderLoderAnimation
Android Content Placeholder Animation like Facebook using Shimmer

We normally use spinner loaders when the app wants to load the data from a network call. Instead of using the usual loaders, we can make the loading screen more interesting using Facebook’s Shimmer library. This library adds Shimmer effect on to any custom view that we define. You can notice this shimmer effect in Facebook’s mobile and desktop apps.

<p align="center">
  <img src="https://raw.githubusercontent.com/appsfeature/PlaceholderLoderAnimation/master/screenshots/shimmer_screen.gif" alt="Preview 1" width="400" /> 
</p>

#### Usage method XML class
```xml 
      <com.facebook.shimmer.ShimmerFrameLayout
          android:id="@+id/shimmer_view_container"
          android:layout_width="match_parent"
          android:layout_height="wrap_content"
          android:orientation="vertical"
          shimmer:shimmer_duration="800" > 
        
          <include layout="@layout/placeholder_item" />

      </com.facebook.shimmer.ShimmerFrameLayout>
                                
```

placeholder_item.xml
```xml 
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:orientation="horizontal"> 
  
    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_weight="1"
        android:gravity="center"
        android:orientation="vertical"
        android:padding="5dp">

        <View
            android:layout_width="50dp"
            android:layout_height="50dp"
            android:layout_marginBottom="5dp"
            android:background="@drawable/bg_circle_placeholder"  />

        <View
            android:layout_width="80dp"
            android:layout_height="10dp"
            android:layout_marginBottom="5dp"
            android:background="@color/placeholder_bg" />

    </LinearLayout>

</LinearLayout>

<color name="placeholder_bg">#dddddd</color>
                                
```
 
#### Usage method Java class
```java 
      mShimmerViewContainer = (ShimmerFrameLayout)findViewById(R.id.shimmer_view_container);

      //show progress animation
      mShimmerViewContainer.startShimmer();
      mShimmerViewContainer.setVisibility(View.VISIBLE);

      //hide progress animation 
      mShimmerViewContainer.stopShimmer(); 
      mShimmerViewContainer.setVisibility(View.GONE);
                                
```
 
