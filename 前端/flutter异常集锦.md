# flutter异常集锦

## 运行中出现问题

问题描述:运行flutter程序时候出现以下提示

```csharp
FAILURE: Build failed with an exception.

* What went wrong:
Could not determine the dependencies of task ':app:compileDebugJavaWithJavac'.
> Could not resolve all task dependencies for configuration ':app:debugCompileClasspath'.
   > Could not find io.flutter:flutter_embedding_debug:1.0.0-fd60ddf7517ce2bfd6577636bda2065c0e492664.
     Required by:
         project :app
   > Could not find io.flutter:arm64_v8a_debug:1.0.0-fd60ddf7517ce2bfd6577636bda2065c0e492664.
     Required by:
         project :app
   > Could not find io.flutter:x86_debug:1.0.0-fd60ddf7517ce2bfd6577636bda2065c0e492664.
     Required by:
         project :app
   > Could not find io.flutter:x86_64_debug:1.0.0-fd60ddf7517ce2bfd6577636bda2065c0e492664.
     Required by:
         project :app
```



​	解决方案:

1. Androidstudio IDE升级为最新版本
2. Android的gradle文件添加

```rust
 maven {
            url 'http://download.flutter.io'
 }
```



------

问题描述:卡在Running Gradle task 'assembleDebug'...   

```flutter
Running Gradle task 'assembleDebug'...    
This is taking an unexpectedly long time.
```

解决方案

1. 修改项目中`android/build.gradle`文件

2. 修改Flutter的配置文件, 该文件在`Flutter安装目录/packages/flutter_tools/gradle/flutter.gradle`

   ```dart
   buildscript {
        repositories {
            //修改的地方
           //google()
            //jcenter()
            maven { url 'https://maven.aliyun.com/repository/google' }
            maven { url 'https://maven.aliyun.com/repository/jcenter' }
            maven { url 'http://maven.aliyun.com/nexus/content/groups/public' }
        }
   
       dependencies {
            classpath 'com.android.tools.build:gradle:3.2.1'
        }
    }
   
   allprojects {
        repositories {
            //修改的地方
           //google()
            //jcenter()
            maven { url 'https://maven.aliyun.com/repository/google' }
            maven { url 'https://maven.aliyun.com/repository/jcenter' }
            maven { url 'http://maven.aliyun.com/nexus/content/groups/public' }
        }
    }
   
   rootProject.buildDir = '../build'
    subprojects {
        project.buildDir = "${rootProject.buildDir}/${project.name}"
    }
    subprojects {
        project.evaluationDependsOn(':app')
    }
   
   task clean(type: Delete) {
        delete rootProject.buildDir
    }
   ```

   ```rust
   buildscript {
        repositories {
            //修改的地方
           //google()
            //jcenter()
            maven { url 'https://maven.aliyun.com/repository/google' }
            maven { url 'https://maven.aliyun.com/repository/jcenter' }
            maven { url 'http://maven.aliyun.com/nexus/content/groups/public' }
        }
        dependencies {
            classpath 'com.android.tools.build:gradle:3.2.1'
        }
    }
   ```

