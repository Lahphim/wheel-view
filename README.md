wheel-view
=========

wheel-view was cloned from this library https://code.google.com/p/android-wheel/ (thank you Yuri Kanivets!!)
You can looking out original demo from this site too.

wheel-view can render wheel view to horizontal, modified base on PasswActivity demo and SlotMachineActivity demo.

Enjoy!!

![1]

Usage
-----

1) Add a custom view in xml
```xml
    ...
    <LinearLayout
        android:layout_width="wrap_content"
        android:layout_height="fill_parent">

        <kankan.wheel.widget.WheelView
            android:id="@+id/slotwheel"
            android:layout_height="wrap_content"
            android:layout_width="wrap_content"/>

    </LinearLayout>
    ...
```

2) Initial wheel view
```java
    WheelView wheel = getWheel(R.id.slotwheel);
    wheel.setViewAdapter(new SlotMachineAdapter(this));
    wheel.setCurrentItem((int)(Math.random() * 10));    // specific position

    wheel.addChangingListener(changedListener);         // add change listener
    wheel.addScrollingListener(scrolledListener);       // add scroll listener
    
    wheel.setCyclic(true);                              // set TRUE to make infinite scroll
    wheel.setEnabled(true);                             // set TRUE to enable scrollable
    wheel.setVertical(false);                           // set FALSE to render as horizontal
    wheel.setInterpolator(new AnticipateOvershootInterpolator());   // set animation
});
```

Customise
---------

1) Customisable dimension of each item
```java
    final int IMAGE_WIDTH = 230;
    final int IMAGE_HEIGHT = 230;
```

2) Customisable all images
```java
    private final int items[] = new int[] {
            android.R.drawable.star_big_on,
            android.R.drawable.stat_sys_warning,
            android.R.drawable.radiobutton_on_background,
            android.R.drawable.ic_delete
    };
```

[1]: ./wheel-view.gif