To initialize the Amplify Predictions and Authentication categories you call `Amplify.addPlugin()` method for each category. To complete initialization call `Amplify.configure()`.

Add the following code to your `onCreate()` method in your application class:

<amplify-block-switcher>
<amplify-block name="Java">

```java
Amplify.addPlugin(new AWSCognitoAuthPlugin());
Amplify.addPlugin(new AWSPredictionsPlugin());
```

Your class will look like this:

```java
public class MyAmplifyApplication extends Application {
    @Override
    public void onCreate() {
        super.onCreate();

        try {
            // Add these lines to add the AWSCognitoAuthPlugin and AWSPredictionsPlugin plugins
            Amplify.addPlugin(new AWSCognitoAuthPlugin());
            Amplify.addPlugin(new AWSPredictionsPlugin());
            Amplify.configure(getApplicationContext());

            Log.i("MyAmplifyApplication", "Initialized Amplify");
        } catch (AmplifyException error) {
            Log.e("MyAmplifyApplication", "Could not initialize Amplify", error);
        }
    }
}
```

</amplify-block>
<amplify-block name="Kotlin">

```kotlin
Amplify.addPlugin(AWSCognitoAuthPlugin())
Amplify.addPlugin(AWSPredictionsPlugin())
```

Your class will look like this:

```kotlin
class MyAmplifyApplication : Application() {
    override fun onCreate() {
        super.onCreate()

        try {
            // Add these lines to add the AWSCognitoAuthPlugin and AWSPredictionsPlugin plugins
            Amplify.addPlugin(AWSCognitoAuthPlugin())
            Amplify.addPlugin(AWSPredictionsPlugin())
            Amplify.configure(applicationContext)

            Log.i("MyAmplifyApplication", "Initialized Amplify")
        } catch (error: AmplifyException) {
            Log.e("MyAmplifyApplication", "Could not initialize Amplify", error)
        }
    }
}
```

</amplify-block>
</amplify-block-switcher>