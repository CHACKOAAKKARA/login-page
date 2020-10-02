package com.example.junefirebase;

import androidx.annotation.NonNull;
import androidx.appcompat.app.AppCompatActivity;

import android.content.Intent;
import android.os.Bundle;
import android.telecom.Call;
import android.util.Log;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.TextView;

import com.example.junefirebase.R;
import com.google.android.gms.tasks.OnCompleteListener;
import com.google.android.gms.tasks.Task;
import com.google.firebase.auth.AuthResult;
import com.google.firebase.auth.FirebaseAuth;

public class MainActivity extends AppCompatActivity {

    EditText email_input;
    EditText password_input;
    Button  button;
    TextView txt_msg;


    FirebaseAuth mAUTH;

    @Override

    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        mAUTH = FirebaseAuth.getInstance();

        email_input = findViewById(R.id.email_input);
        password_input = findViewById(R.id.passwoord_input);
        button = findViewById(R.id.button);
        txt_msg= findViewById(R.id.txt_msg);



        button.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {

                String email = email_input.getText().toString();
                String password = password_input.getText().toString();


                mAUTH.createUserWithEmailAndPassword(email,password)
                        .addOnCompleteListener( new OnCompleteListener<AuthResult>() {
                            @Override
                            public void onComplete(@NonNull Task<AuthResult> task) {

                                if (task.isSuccessful()){
                                    txt_msg.setText("new user");
                                }else{
                                    txt_msg.setText("error");
                                }

                            }
                        });

            }

        });
    }
}
