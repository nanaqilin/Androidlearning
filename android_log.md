# Android 调试log的方法 #
****
相关代码
> public static final String TAG = MainActivity.class.getSimpleName();

> android.util.Log.i(TAG,"my test hello activity");
****

# Android Toast 的使用 #
****
相关代码如下：
> Context context = getApplicationContext();
> CharSequence text = "My Hello toast!";
> int duration = Toast.LENGTH_SHORT;

> Toast toast = Toast.makeText(context, text, duration);
> toast.show();
****