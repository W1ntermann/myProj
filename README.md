# myProj
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
              android:orientation="vertical"
              android:layout_width="fill_parent"
              android:layout_height="fill_parent"
        >

    <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Enter ur name:"
            android:id="@+id/textView" android:layout_gravity="left|center_vertical"/>
    <EditText
            android:layout_width="167dp"
            android:layout_height="wrap_content"
            android:id="@+id/name" android:layout_gravity="left|center_vertical"/>
    <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Enter ur Last name:"
            android:id="@+id/textView1" android:layout_gravity="left|center_vertical"/>
    <EditText
            android:layout_width="169dp"
            android:layout_height="wrap_content"
            android:id="@+id/lastname" android:layout_gravity="left|center_vertical"/>
    <Button
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Go to Activity"
            android:id="@+id/btnActTwo"
            android:onClick="goNewView" android:layout_gravity="left|center_vertical"/>

</LinearLayout>

second.xml

<?xml version="1.0" encoding="utf-8"?>

<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
              android:orientation="vertical"
              android:layout_width="match_parent"
              android:layout_height="match_parent">

    <TextView
            android:id="@+id/nametxt"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Ur name:" />
    <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Ur lastName: "
            android:id="@+id/lastnametxt" android:layout_gravity="left|center_vertical"/>
    <Button
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Retreat"
            android:onClick="back"
            android:id="@+id/back_button" android:layout_gravity="left|center_vertical"/>

     </LinearLayout>

    package com.example.GoActivity;

    import android.app.Activity;
    import android.content.Intent;
    import android.os.Bundle;
    import android.view.View;
    import android.widget.Button;
    import android.widget.EditText;

    public class MainActivity extends Activity {

    private Button forward;
    private EditText name;
    private EditText lastName;

    @Override
    public void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.main);

        forward = (Button) findViewById(R.id.btnActTwo);
        name = (EditText) findViewById(R.id.name);
        lastName = (EditText) findViewById(R.id.lastname);
    }
    
}

//second activity

    package com.example.GoActivity;

    import android.app.Activity;
    import android.content.Intent;
    import android.os.Bundle;
    import android.view.View;
    import android.widget.Button;
    import android.widget.EditText;
    import android.widget.TextView;

    public class NewActivity extends Activity {

    private Button back;
    private TextView name;
    private TextView lastName;

    public void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.two);

        back = (Button) findViewById(R.id.back_button);
        name = (TextView) findViewById(R.id.nametxt);
        lastName = (TextView) findViewById(R.id.lastnametxt);
        
        String txtName = getIntent().getStringExtra("name");


        String txtLastname = getIntent().getStringExtra("lastname");

        
        name.setText(name.getText().toString() + " " + txtName);


        lastName.setText(lastName.getText().toString() + " " + txtLastname);
        

    public void back(View v){
    switch (v.getId()) {
        case R.id.back_button:
            Intent intent = new Intent(this, MainActivity.class);
            startActivity(intent);
            break;
        default:
            break;
         }
             }                                                 
             }
                }





