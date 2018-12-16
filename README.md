# CameraView

*基于Google官方API，并进行相关维护。*

CameraView旨在帮助Android开发者便于集成相机功能。

支持API 9及以上版本。该库在API 9-20版本使用Camera 1 API，在21及以上版本使用Camera2 API。

| API Level | Camera API | Preview View |
|:---------:|------------|--------------|
| 9-13      | Camera1    | SurfaceView  |
| 14-20     | Camera1    | TextureView  |
| 21-23     | Camera2    | TextureView  |
| 24        | Camera2    | SurfaceView  |

## 特性

- 可以将相机预览界面置入到一个布局XML文件中（需调用start方法）
- 属性配置
  - 纵横比 (app:aspectRatio)
  - 是否自动对焦 (app:autoFocus)
  - 闪光灯 (app:flash)

## 用法

```xml
<com.google.android.cameraview.CameraView
    android:id="@+id/camera"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:keepScreenOn="true"
    android:adjustViewBounds="true"
    app:autoFocus="true"
    app:aspectRatio="4:3"
    app:facing="back"
    app:flash="auto"/>
```

```java
    @Override
    protected void onResume() {
        super.onResume();
        mCameraView.start();
    }

    @Override
    protected void onPause() {
        mCameraView.stop();
        super.onPause();
    }
```

在示例app中可以看到完整的使用代码。

## 贡献

详见 [CONTRIBUTING.md](/CONTRIBUTING.md).
