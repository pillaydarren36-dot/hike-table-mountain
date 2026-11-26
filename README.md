# Hike Table Mountain: build the Android app

You need: Node.js (nodejs.org) and Android Studio (developer.android.com/studio).

1. Unzip, open a terminal in this folder.
2. npm install
3. Offline 3D map: copy node_modules/three/build/three.min.js into www/ and in www/index.html
   change the three.js <script src="https://cdnjs..."> to <script src="three.min.js">.
4. npx cap add android
5. Open android/app/src/main/AndroidManifest.xml and add inside <manifest>:
   <uses-permission android:name="android.permission.ACCESS_FINE_LOCATION"/>
   <uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION"/>
6. npx cap sync android
7. npx cap open android
8. In Android Studio: Build > Build Bundle(s)/APK(s) > Build APK(s).
   The APK is in android/app/build/outputs/apk/debug. Copy it to your phone and tap it to install
   (allow "install unknown apps" when asked).
9. For Google Play: Build > Generate Signed Bundle (AAB) and upload that.

## No Android Studio? Build it free on GitHub
1. Create a free account at github.com and make a new repository (branch name: main).
2. Upload all files from this folder (including the hidden .github folder).
3. Open the Actions tab > Build APK > Run workflow. Wait about 5 minutes.
4. Open the finished run, download "hike-table-mountain-apk", unzip, and install app-debug.apk on your phone.
