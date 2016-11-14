# ChangeL
Cambio de idioma mediante programación en Android

```
public class MainApplication extends Application {
    @Override
    public void onCreate() {
        super.onCreate();
        LocaleHelper.onCreate(this, "en");
}
```
