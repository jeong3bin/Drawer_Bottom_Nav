# Drawer_Bottom_Nav
Application that have Navigation and Bottom Navigation


### Drawer Navigation custom
`drawer_layout.xml`에서 Drawer Navigaton의 custom이 가능하다.  
MainActivity.kt에서 view control 가능

#### activity_main_drawer.xml
```kotlin
<?xml version="1.0" encoding="utf-8"?>
<menu xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    tools:showIn="navigation_view">

    <group android:checkableBehavior="single">
        <item
            android:id="@+id/nav_home"
            android:icon="@drawable/ic_menu_camera"
            android:title="@string/menu_home" />
        <item
            android:id="@+id/nav_gallery"
            android:icon="@drawable/ic_menu_gallery"
            android:title="@string/menu_gallery" />
        <item
            android:id="@+id/nav_slideshow"
            android:icon="@drawable/ic_menu_slideshow"
            android:title="@string/menu_slideshow" />
        <item
            android:id="@+id/nav_tools"
            android:icon="@drawable/ic_menu_manage"
            android:title="@string/menu_tools" />
    </group>

    <item android:title="Communicate">
        <menu>
            <item
                android:id="@+id/nav_share"
                android:icon="@drawable/ic_menu_share"
                android:title="@string/menu_share" />
            <item
                android:id="@+id/nav_send"
                android:icon="@drawable/ic_menu_send"
                android:title="@string/menu_send" />
        </menu>
    </item>

</menu>
```

### Bottom Navigation
`bottom_nav_menu.xml` 파일과 `mobile_navigation.xml` 파일 동시에 변경 후  
`MainActivity.kt` 파일의 아래 부분 변경 시 fragment 갯수 변경 가능
```kotlin
appBarConfiguration = AppBarConfiguration(
            setOf(
                R.id.navigation_main,R.id.navigation_sub
            ),drawerLayout
        )
```


#### 오류  
> _cannot inline bytecode built with jvm target 1.8 into bytecode that is being built with jvm target 1.6. please specify proper '-jvm-target' option_
+ __gradle(app)__  
    android { } 안에 입력 후 `sync now` 
    ```kotlin
    kotlinOptions{
        jvmTarget="1.8"
    }
    ```

