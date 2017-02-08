---
layout: post
category: "Android"
---


Workaround for https://code.google.com/p/android/issues/detail?id=182715

The Android Gradle plugin is creating DataBindingExportBuildInfoTasks for the instrumentation APK that generates from the app APKs layouts. This creates duplicate classes in the app and instrumentation APK which leads to
 
 
`java.lang.IllegalAccessError: Class ref in pre-verified class resolved to unexpected implementation on older devices`
 
The workaround is to get the DataBindingExportBuildInfoTasks tasks for the instrumentation APK and delete the files right after it creates them.

## Solution

```
tasks.withType(DataBindingExportBuildInfoTask) { task ->
    if (task.name.endsWith("AndroidTest")) {
        task.finalizedBy(tasks.create("${task.name}Workaround") << {
            task.output.deleteDir()
        })
    }
}
```
