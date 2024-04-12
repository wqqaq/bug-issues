#### com.mbti.wikimbti

com.mbti.wikimbti has an Android manifest file that contains an entry with the android:allowBackup attribute set to true. This could be leveraged by an attacker with physical access to the device.

- package: com.mbti.wikimbti
- version: 0.2
- url: https://os-android.liqucn.com/rj/9639961891368.shtml

```xml
<application android:theme="@style/Theme.WikiMbti.SplashScreen" android:label="@string/app_name" android:icon="@mipmap/ic_launcher" android:name="com.mbti.wikimbti.WikiMbtiApplication" android:allowBackup="true" android:supportsRtl="true" android:extractNativeLibs="false" android:fullBackupContent="@xml/backup_rules" android:usesCleartextTraffic="true" android:networkSecurityConfig="@xml/network_security_config" android:appComponentFactory="androidx.core.app.CoreComponentFactory" android:dataExtractionRules="@xml/data_extraction_rules" android:enableOnBackInvokedCallback="true">
```

poc

```shell
adb backup -apk -shared -f backup.ab com.mbti.wikimbti 
```

![image-20240412174348699](image-20240412174348699.png)