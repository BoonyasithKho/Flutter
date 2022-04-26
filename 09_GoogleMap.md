# Google Map
- การติดตั้ง Google Maps for Flutter เบื้องต้น
  1. ขอ API Key จากลิงค์ https://cloud.google.com/maps-platform/
  2. ทำการ Enable เพื่อที่จะเรียกใช้ API (Enable Maps SDK for Android / IOS)
  3. เข้าไปที่เมนู Credentials เพื่อที่จะสร้าง API Key เอาไปแปะในโค้ดให้เชื่อมต่อกับ Google Cloud Platform
      Create Credentials -> API Key
- นำ API Key มาใช้
  - Android : เพิ่ม API Key ที่ไฟล์ AndroidManifest.xml ในโฟลเดอร์ android/app/src/main/AndroidManifest.xml
    ```
    <manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="com.example.fluttergooglemap">
    // ส่วนที่เพิ่มเติม เพื่อทำการกำหนด Permission
    <uses-permission android:name="android.permission.ACCESS_FINE_LOCATION"/>
    <uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION"/>

    <application
        android:name="io.flutter.app.FlutterApplication"
        android:label="fluttergooglemap"
        android:icon="@mipmap/ic_launcher">
        // ส่วนที่เพิ่มเติม นำ API Key ที่ได้มาแทนใน "YOUR API KEY"
        <meta-data android:name="com.google.android.geo.API_KEY"
            android:value="YOUR API KEY"/>

        <activity
            android:name=".MainActivity"
            ...
     ```
     Set the minSdkVersion in android/app/build.gradle:
     ```
     android {
        defaultConfig {
            minSdkVersion 20 // เดิมเป็น minSdkVersion flutter.minSdkVersion
          }
      }
      ```
  - iOS : เข้าไปที่ไฟล์ AppDelegate.swift (ios/Runner/AppDelegate.swift) เพิ่ม API KEY เข้าไป GMSServices.provideAPIKey("YOUR KEY HERE")
    ```
    @UIApplicationMain
    @objc class AppDelegate: FlutterAppDelegate {
      override func application(
        _ application: UIApplication,
        didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?
      ) -> Bool {
      GMSServices.provideAPIKey("YOUR API KEY")
        GeneratedPluginRegistrant.register(with: self)
        return super.application(application, didFinishLaunchingWithOptions: launchOptions)
      }
    }
    ```
    และเข้าไปที่ไฟล์ info.plist เพิ่มคำสั่ง เพื่อขอ permission
    ```
    <dict>
     <key>NSLocationWhenInUseUsageDescription</key>
          <string>This app needs your location to test the location feature of the Google Maps plugin.</string>
          <key>io.flutter.embedded_views_preview</key>
          <true/>
     ...
    ```
  - ติดตั้ง google_maps_flutter จาก pub.dev ใน pubspec.yaml
  - import Library
    ```
    import 'package:google_maps_flutter/google_maps_flutter.dart';
    ```
  - สร้างตัวแปรประเภท GoogleMapController โดยเป็น class ที่เอาไว้สร้าง Future สำหรับควบคุมการทำงาน
    ```
    class _MyHomePageState extends State<MyHomePage> {
      Completer<GoogleMapController> _controller = Completer();
    ```
  - การใช้งาน GoogleMap จะต้องทำการ initialCameraPosition เสมอ เพื่อกำหนดพิกัดจุดเริ่มต้นสถานที่ให้ GoogleMap ทำการแสดงผล
    ```
    body: GoogleMap(
        initialCameraPosition: CameraPosition(
          target: LatLng(13.757429, 100.502465), //กำหนดพิกัดเริ่มต้นบนแผนที่
          zoom: 15, //กำหนดระยะการซูม สามารถกำหนดค่าได้ 0-20
        ),
        onMapCreated: (GoogleMapController controller) {
          _controller.complete(controller);
        },
      ),
    ```
