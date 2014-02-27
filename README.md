Volley-Singleton
================

A common RequestQueue object for your Android app using Google Volley in the form of a Singleton.

The singleton provides access to static RequestQueue and ImageLoader objects via its two methods:
```Java
    public RequestQueue getRequestQueue(){
        return this.mRequestQueue;
    }
    
    public ImageLoader getImageLoader(){
        return this.mImageLoader;
    }
```
#Setup

##Import Google Volley
Import the Google Volley Library into your Android project

https://android.googlesource.com/platform/frameworks/volley/

##Add VolleySingleton.java
Include the VolleySingleton.java class from this repository in your Android application. 

##Use it in your code
**Import the Volley packages**

```Java

    import com.android.volley.VolleyError;
    import com.android.volley.toolbox.ImageLoader;
    import com.android.volley.toolbox.NetworkImageView;
```

**Instantiate an ImageLoader variable**

```Java
    private ImageLoader mImageLoader;
```

**Initialize the ImageLoader variable in your OnCreate() method**

```Java

    @Override
    public void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);

        mImageLoader = VolleySingleton.getInstance(this.getActivity()).getImageLoader();
    }
```

**Use it where appropriate**

```Java
     NetworkImageView avatar = (NetworkImageView)view.findViewById(R.id.twitter_avatar);
     avatar.setImageUrl("http://someurl.com/image.png",mImageLoader);
```
