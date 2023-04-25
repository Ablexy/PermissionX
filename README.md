# PermissionX

PermissionX是一个用于简化Android运行时权限用法的开源库。

添加如下配置将PermissionX引入到你的项目当中：

```groovy
Step 1. Add the JitPack repository to your build file

Add it in your root build.gradle at the end of repositories:

        allprojects {
            repositories {
                ...
                maven { url 'https://jitpack.io' }
            }
        }
Step 2. Add the dependency

dependencies {
    ...
    implementation 'com.github.Ablexy:PermissionX:0.0.2'
}
```

然后就可以使用如下语法结构来申请运行时权限了：

```kotlin
PermissionX.request(this,
                Manifest.permission.CALL_PHONE,
                Manifest.permission.READ_CONTACTS) { allGranted, deniedList ->
    if (allGranted) {
        Toast.makeText(this, "All permissions are granted", Toast.LENGTH_SHORT).show()
    } else {
        Toast.makeText(this, "You denied $deniedList", Toast.LENGTH_SHORT).show()
    }
}
```




