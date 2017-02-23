---
layout: post
category: "Android"
---



## Add submodules

```
cd <project_root>
mkdir -p libraries
git submodule add <path-to-remote-repo>
```

## Edit settings.gradle to add
```
':libraries:custom-library'
```

### For library repo which has sample project like vivid
```
include ':app', ':vivid:library'
project(':vivid').projectDir = new File('vivid/library')
```

## Open <project_root>/app/build.gradle and add:

```
compile project(':libraries:custom-library')
```
