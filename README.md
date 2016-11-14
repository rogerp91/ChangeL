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
# Usage
public class TestActivity extends AppCompatActivity {
    @Bind(R.id.titleTextView) TextView mTitleTextView;
    @Bind(R.id.descTextView) TextView mDescTextView;
    @Bind(R.id.aboutTextView) TextView mAboutTextView;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
    }

    @OnClick(R.id.englishButton)
    public void onEnglishClick() {
        LocaleHelper.setLocale(this, "en");
        updateViews();
    }

    @OnClick(R.id.turkishButton)
    public void onTurkishClick() {
        LocaleHelper.setLocale(this, "tr");
        updateViews();
    }

    private void updateViews() {
        // if you want you just call activity to restart itself to redraw all the widgets with the correct locale
        // however, it will cause a bad look and feel for your users
        //
        // this.recreate();
      
        //or you can just update the visible text on your current layout
        Resources resources = getResources();

        mTitleTextView.setText(resources.getString(R.string.title_text));
        mDescTextView.setText(resources.getString(R.string.desc_text));
        mAboutTextView.setText(resources.getString(R.string.about_text));
    }
}
