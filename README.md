### Simple To-Do List App for Android Workshop

Here's a step-by-step guide to create a simple To-Do List app using XML and Java in Android Studio. This app allows users to add tasks to a list and remove them by clicking on the task. 
This simple app covers basic concepts of Android development like layout design, event handling, and working with lists. 

#### 1. **Create a New Project in Android Studio**

- **Step 1:** Open Android Studio and select "New Project."
- **Step 2:** Choose "Empty Activity" and click "Next."
- **Step 3:** Name your project "SimpleToDoList" (or any name you prefer).
- **Step 4:** Set the "Language" to Java.
- **Step 5:** Choose "API 21: Android 5.0 (Lollipop)" or higher as the Minimum API level.
- **Step 6:** Click "Finish" to create the project.

#### 2. **Design the Layout (XML)**

Create the layout for the app in the `activity_main.xml` file.

**File:** `res/layout/activity_main.xml`

```xml
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:padding="16dp">

    <EditText
        android:id="@+id/taskInput"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="@string/enter_task"
        android:inputType="text"
        android:importantForAutofill="yes"
        android:autofillHints="task"
        android:padding="12dp" />

    <Button
        android:id="@+id/addTaskButton"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="@string/add_task"
        android:layout_below="@id/taskInput"
        android:layout_marginTop="16dp"
        android:minWidth="120dp"
        android:padding="12dp" />

    <ListView
        android:id="@+id/taskListView"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_below="@id/addTaskButton"
        android:layout_marginTop="16dp"
        android:listSelector="@android:color/transparent"
        android:dividerHeight="1dp" />
</RelativeLayout>
```

#### 3. **Add Strings (Text Resources)**

Define the strings used in the app in the `strings.xml` file to avoid hardcoding.

**File:** `res/values/strings.xml`

```xml
<resources>
    <string name="app_name">SimpleToDoList</string>
    <string name="enter_task">Enter a task</string>
    <string name="add_task">Add Task</string>
</resources>
```

#### 4. **Add Functionality with Java**

Implement the logic to handle task input, adding tasks to the list, and removing tasks when clicked.

**File:** `src/main/java/com/example/simpletodolist/MainActivity.java`

```java
package com.example.simpletodolist;

import android.os.Bundle;
import android.widget.ArrayAdapter;
import android.widget.Button;
import android.widget.EditText;
import android.widget.ListView;

import androidx.appcompat.app.AppCompatActivity;

import java.util.ArrayList;

public class MainActivity extends AppCompatActivity {

    private ArrayList<String> tasks;
    private ArrayAdapter<String> adapter;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        EditText taskInput = findViewById(R.id.taskInput);
        Button addTaskButton = findViewById(R.id.addTaskButton);
        ListView taskListView = findViewById(R.id.taskListView);

        tasks = new ArrayList<>();
        adapter = new ArrayAdapter<>(this, android.R.layout.simple_list_item_1, tasks);
        taskListView.setAdapter(adapter);

        addTaskButton.setOnClickListener(v -> {
            String task = taskInput.getText().toString();
            if (!task.isEmpty()) {
                tasks.add(task);
                adapter.notifyDataSetChanged();
                taskInput.setText("");
            }
        });

        taskListView.setOnItemClickListener((parent, view, position, id) -> {
            tasks.remove(position);
            adapter.notifyDataSetChanged();
        });
    }
}
```

#### 5. **Run Your App**

- **Step 1:** Connect an Android device or start an emulator.
- **Step 2:** Click the "Run" button in Android Studio to build and launch your app.
