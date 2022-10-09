# Speak

## Summary

The base of this project is Android Text to Speech. While reading, I come across some heavy words that are hard to pronounce. Android 6.0 Marshmallow introduced a new floating text selection toolbar, which brings the standard text selection actions, like cut, copy, and paste, closer to the text you’ve selected. Even better though is the new `ACTION_PROCESS_TEXT` which makes it possible for any app to add custom actions to that text selection toolbar.


![alt text](https://cdn-images-1.medium.com/max/1600/1*D4zZzPlBTk5cEN9Qn0-cBA.gif)


Taking advantage of this feature, this app passes the selected text to itself and speaks it out.

## Downloads

Download the `.apk` file or the source code here.

Apk : 
[Speak.apk](https://github.com/NachiketaVadera/Speak/releases/download/v1.0/nachiketaVadera-Speak-v1.0.apk)

Zip :
[Speak.zip](https://github.com/NachiketaVadera/Speak/archive/v1.0.zip)

Tar.gz :
[Speak.tar.gz](https://github.com/NachiketaVadera/Speak/archive/v1.0.tar.gz)

## Code

The majority of the code is written in Java and is simple. For enabling custom text selection:

(1.) AndroidManifest.xml
```xml
      <activity android:name=".MainActivity" android:windowSoftInputMode="stateAlwaysVisible">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />

                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>

            <intent-filter>
                <action android:name="android.intent.action.PROCESS_TEXT"/>

                <category android:name="android.intent.category.DEFAULT" />

                <data android:mimeType="text/*"/>
            </intent-filter>
        </activity>
```

(2.) MainActivity.java
```java
      @Override
      protected void onCreate(Bundle savedInstanceState) {
          super.onCreate(savedInstanceState);
          setContentView(R.layout.process_text_main);
          CharSequence text = getIntent().getCharSequenceExtra(Intent.EXTRA_PROCESS_TEXT);
          // process the text
      }
```

## Contributing

Any help, including feedback, is highly appreciated. I have just started out with Android and I’m relatively new to app development.

1. Fork it!
2. Create your feature branch: `git checkout -b new-branch`
3. Commit your changes: `git commit -am 'Make a valuable addition'`
4. Push to the branch: `git push origin new-feature`
5. Submit a pull request :D

## Next Step

Once started, an app can never be completely finished. 

* Try to make a service out of the app.
