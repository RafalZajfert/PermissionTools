# PermissionTools
Library for simplify android permissions management

##Gradle Dependency (jCenter)

```Gradle
dependencies {
    compile 'com.rafalzajfert:permission-tools:1.0.0'
}
```

[ ![Download](https://api.bintray.com/packages/rafalzajfert/maven/permission-tools/images/download.svg) ](https://bintray.com/rafalzajfert/maven/permission-tools/_latestVersion)

##Maven Dependency

```Maven
<dependency>
    <groupId>com.rafalzajfert</groupId>
    <artifactId>permission-tools</artifactId>
    <version>1.0.0</version>
</dependency>
```

##Sample Usage

```java
public void checkPermissionAndTakePhoto(){
    Permissions.checkPermission(this, new OnPermissionResultTask() {
        @Override
        public void onPermissionGranted(@NonNull String[] permissions) throws SecurityException {
            takePhoto();
        }

        @Override
        public void onPermissionDenied(@NonNull String[] grantedPermissions, @NonNull String[] deniedPermissions) {
            Toast.makeText(this, "Permissions denied!", Toast.LENGTH_LONG).show();
        }
    }, Manifest.permission.CAMERA, Manifest.permission.WRITE_EXTERNAL_STORAGE);
}

@Override
public void onRequestPermissionsResult(int requestCode, @NonNull String[] permissions, @NonNull int[] grantResults) {
    super.onRequestPermissionsResult(requestCode, permissions, grantResults);
    Permissions.onRequestPermissionsResult(requestCode, permissions, grantResults);
}
```

**Method onPermissionDenied(String[], String[]) is optional*

##Developed By

 * Rafal Zajfert - <rafal.zajfert@gmail.com>

##License

    Copyright 2016 Rafal Zajfert

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
