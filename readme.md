# Android Network Manager

![Androd Network Manager](https://i2.wp.com/androidstudy.com/wp-content/uploads/2017/09/2706bd7be409dfabb029d003594682e6.jpg?zoom=2&resize=1038%2C576)

A Simple Android library to check various types of network connections, to allow an app check internet connectivity status before making HTTP Requests.

## Getting Started

These instructions will help you set up this library easily on your current project and working in no time. You only need a few configurations to start working!

## Installing

To be able to use the following library, you will need to add the following gradle dependency in your build.gradle(module:app) file

```
compile 'com.github.jumadeveloper:networkmanager:0.0.2'
```

Sync Project, and start using the library instantly on your project.

If you are using Maven, add it using :

```
<dependency>
  <groupId>com.github.jumadeveloper</groupId>
  <artifactId>networkmanager</artifactId>
  <version>0.0.2</version>
  <type>pom</type>
</dependency>
```
That is the basic set up needed to be able to use the library in your applications!

## Permissions

A step by step to set up Android Network Manager in your project.

First, we need to add this permission to our Android Manifest file :

```
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE"/>
```

If you are using this Library, this means your Application is using Internet, so don't forget the following permission also:

```
<uses-permission android:name="android.permission.INTERNET"/>
```

Also, for android M and above, you must request the runtime permission for `ACCESS_NETWORK_STATE`.

That's it, you have set up the required permissions and ready to go!

## Quick Example

You can use it in both Android Activities and Fragments, as shown using the code snippets below. You can now replace the toasts with a call to make your HTTP Request now!
```
import com.androidstudy.networkmanager.Monitor;
import com.androidstudy.networkmanager.Tovuti;
...

public class MyActivity extends Activity {
    private Tovuti tovuti;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(...);

        tovuti = Tovuti.from(this)
                .monitor(new Monitor.ConnectivityListener() {
                    @Override
                    public void onConnectivityChanged(int connectionType, boolean isConnected, boolean isFast) {
                        ...
                    }
                });
    }

    @Override
    protected void onStop() {
        super.onStop();
        tovuti.stop();
    }
}
```

## Contributing and Issues

Please feel free to contribute or open issues, if any and I will be happy to help out!

## Authors

* **Juma Allan** - Android Developer, [Muva Technologies Ltd](http://muva.co.ke)
* **Elvis Chweya** - Android developer

## License

This project is licensed under the MIT License.

## Acknowledgments

* Juma Allan
* [Elvis Chweya](https://github.com/chweez)
