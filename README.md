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

                                            XML
<?xml version="1.0" encoding="utf-8"?>
<android.support.constraint.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context="com.example.chinmay.firebase.MainActivity">

    <Button
        android:id="@+id/button1"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Save"
        android:onClick="save"
        tools:layout_editor_absoluteX="148dp"
        tools:layout_editor_absoluteY="257dp" />

    <EditText
        android:id="@+id/editText1"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:ems="10"
        android:inputType="textPersonName"
        android:text="Products"
        tools:layout_editor_absoluteX="48dp"
        tools:layout_editor_absoluteY="33dp" />

    <EditText
        android:id="@+id/editText2"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:ems="10"
        android:inputType="textPersonName"
        android:text="Name"
        tools:layout_editor_absoluteX="48dp"
        tools:layout_editor_absoluteY="114dp" />

</android.support.constraint.ConstraintLayout

                                            MainActivity.java
package com.example.chinmay.firebase;
import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;

import com.google.firebase.FirebaseApp;

public class MainActivity extends AppCompatActivity {
    private Button save;
    private EditText products,name;
    private Firebase mref;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        save=(Button)findViewById(R.id.button1);
        products=(EditText)findViewById(R.id.editText1);
        name=(EditText)findViewById(R.id.editText2);
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        mref= new Firebase['https://fir-b1318.firebaseio.com/'];
        Firebase.setAndroidContext(this);
        b.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                String value1=products.getText().toString();
                String key1=name.getText().toString();
                Firebase mrefchild = mref.child(key1);

                mrefchild.setValue(value1);
            }
        });

    }
}


