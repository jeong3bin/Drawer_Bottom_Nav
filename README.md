# Drawer_Bottom_Nav
Application that have Navigation and Bottom Navigation
  
#### 오류  
> _cannot inline bytecode built with jvm target 1.8 into bytecode that is being built with jvm target 1.6. please specify proper '-jvm-target' option_
+ __gradle(app)__  
    android { } 안에 입력 후 `sync now` 
    ```kotlin
    kotlinOptions{
        jvmTarget="1.8"
    }
    ```

