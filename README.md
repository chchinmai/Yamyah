                                               fire base
buildscript {
    repositories {
        jcenter()
    }
    dependencies {
        classpath 'com.android.tools.build:gradle:2.3.0'
        classpath 'com.google.gms:google-services:3.0.0'
        // NOTE: Do not place your application dependencies here; they belong
        // in the individual module build.gradle files
    }
}

allprojects {
    repositories {
        jcenter()
    }
}

task clean(type: Delete) {
    delete rootProject.buildDir
}
                 
                 
                 
                                                 // app    ->build.gradle 
apply plugin: 'com.android.application'

android {
    compileSdkVersion 25
    buildToolsVersion "25.0.2"
    defaultConfig {
        applicationId "com.example.chinmai.firebase"
        minSdkVersion 17
        targetSdkVersion 25
        versionCode 1
        versionName "1.0"
        testInstrumentationRunner "android.support.test.runner.AndroidJUnitRunner"
    }
    buildTypes {
        release {
            minifyEnabled false
            proguardFiles getDefaultProguardFile('proguard-android.txt'), 'proguard-rules.pro'
        }
    }
}

dependencies {
    compile fileTree(dir: 'libs', include: ['*.jar'])
    androidTestCompile('com.android.support.test.espresso:espresso-core:2.2.2', {
        exclude group: 'com.android.support', module: 'support-annotations'
    })
    compile 'com.android.support:appcompat-v7:25.3.1'
    compile 'com.android.support.constraint:constraint-layout:1.0.2'
    compile 'com.google.firebase:firebase-database:10.2.1'
    testCompile 'junit:junit:4.12'
}
apply plugin: 'com.google.gms.google-services'

                                    //googleservice.json
{
  "project_info": {
    "project_number": "391651880324",
    "firebase_url": "https://fir-b1318.firebaseio.com",
    "project_id": "fir-b1318",
    "storage_bucket": "fir-b1318.appspot.com"
  },
  "client": [
    {
      "client_info": {
        "mobilesdk_app_id": "1:391651880324:android:c8661fba9a275ecb",
        "android_client_info": {
          "package_name": "com.example.chinmai.firebase"
        }
      },
      "oauth_client": [
        {
          "client_id": "391651880324-d0vlj2t2bc6lrbqc3gp93o2uc0s38lcj.apps.googleusercontent.com",
          "client_type": 3
        }
      ],
      "api_key": [
        {
          "current_key": "AIzaSyAtmKEU2Ybk7j3yy5fMqfysrl8M25TZGH8"
        }
      ],
      "services": {
        "analytics_service": {
          "status": 1
        },
        "appinvite_service": {
          "status": 1,
          "other_platform_oauth_client": []
        },
        "ads_service": {
          "status": 2
        }
      }
    }
  ],
  "configuration_version": "1"
}
