Phonegap
-------
Change your sdk in the pom.xml and local.properties (not sure if both are needed, but I change both).

You need to install the cordova/phonegap/callback/whatever android JAR manually into your local maven repository, using:

    Use mvn install:install-file -DgroupId=org.apache.cordova -DartifactId=cordova -Dversion=2.0.0 -Dfile=<YOUR_PHONEGAP_ANDROID_JAR>  -Dpackaging=jar

Then run:

    mvn -Dandroid.sdk.path=<YOUR_SDK_PATH> clean install android:apk
    mvn android:emulator-start
    mvn android:deploy

This should create an APK for you which can then be installed.

android.sdk.path=/opt/android-sdk on my system.

http://maven-android-plugin-m2site.googlecode.com/svn/plugin-info.html
