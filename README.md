# Activity Lifecycle Introduction (with Logcat output)

activitylifecycleintroduction-melvincabatuan created by Classroom for GitHub

This assignment illustrates the Android activity lifecycle using Logcat.

## Problem:

Implement an Android application that displays Logs in Logcat when the following methods are called:

1. *onCreate()* - handles the creation of the activity object, and the loading of any static resources like themes, images, layouts, set up menus, and the like.

2. *onStart()* - executes every time the activity begins.

3. *onResume()* - executes when the activity is making a transition from the Paused state and into the Running state again.

4. *onPause()* - called when the activity is still partially visible.

5. *onSaveInstanceState()* - called before the activity gets destroyed, which means you get an opportunity to save any variables you want to retain.

6. *onStop()* - called when the activity is no longer visible on the screen.

7. *onRestart()* - called when activity was stopped but is started again later.

8. *onDestroy()* - called when the entire app is being shut down and unloaded from memory.


## Basig Logging:

```Java
  private static final String DEBUG_TAG = "MainActivity";
  ...
      @Override
    protected void onStart() {
        super.onStart();
        Log.d(DEBUG_TAG, "onStart() method was called... (Tinawag po ang onStart())");
    }
    ...
```


## Accept

To accept the assignment, click the following URL:

 https://classroom.github.com/assignment-invitations/49b719d170d4a965a8872304db995678  


## Sample Solution:

https://github.com/DeLaSalleUniversity-Manila/activitylifecycleintroduction-melvincabatuan


## Keypoints:

On App Launch:

```shell
10-02 16:51:28.393 32431-32431/com.cabatuan.lifecycleintroduction D/MainActivity: onCreate() method was called... (Tinawag po ang onCreate())
10-02 16:51:28.393 32431-32431/com.cabatuan.lifecycleintroduction D/MainActivity: onStart() method was called... (Tinawag po ang onStart())
10-02 16:51:28.394 32431-32431/com.cabatuan.lifecycleintroduction D/MainActivity: onResume() method was called... (Tinawag po ang onResume())
```


On Android 'Home' button press: 
```shell
10-02 16:54:27.411 32431-32431/com.cabatuan.lifecycleintroduction D/MainActivity: onPause() method was called... (Tinawag po ang onPause())
10-02 16:54:27.412 32431-32431/com.cabatuan.lifecycleintroduction D/ActivityThread: ACT-AM_ON_PAUSE_CALLED ActivityRecord{42719368 token=android.os.BinderProxy@42718a28 {com.cabatuan.lifecycleintroduction/com.cabatuan.lifecycleintroduction.MainActivity}}
10-02 16:54:27.422 32431-32431/com.cabatuan.lifecycleintroduction D/ActivityThread: ACT-PAUSE_ACTIVITY handled : 1 / android.os.BinderProxy@42718a28
10-02 16:54:27.595 32431-32431/com.cabatuan.lifecycleintroduction D/OpenGLRenderer: Flushing caches (mode 0)
10-02 16:54:27.596 32431-32431/com.cabatuan.lifecycleintroduction D/GraphicBuffer: close handle(0x60f46d08) (w:720 h:1280 f:1)
10-02 16:54:28.030 32431-32431/com.cabatuan.lifecycleintroduction D/MainActivity: onSaveInstanceState() method was called... (Tinawag po ang onSaveInstanceState())
10-02 16:54:28.030 32431-32431/com.cabatuan.lifecycleintroduction D/MainActivity: onStop() method was called... (Tinawag po ang onStop())
```


On relaunch of the App: (Notice that onCreate() was no longer called)
```shell
10-02 16:57:57.971 32431-32431/com.cabatuan.lifecycleintroduction D/MainActivity: onRestart() method was called... (Tinawag po ang onRestart())
10-02 16:57:57.971 32431-32431/com.cabatuan.lifecycleintroduction D/MainActivity: onStart() method was called... (Tinawag po ang onStart())
10-02 16:57:57.971 32431-32431/com.cabatuan.lifecycleintroduction D/MainActivity: onResume() method was called... (Tinawag po ang onResume())
```


On Android 'Back' button press:
```shell
10-02 16:58:51.083 32431-32431/com.cabatuan.lifecycleintroduction D/MainActivity: onPause() method was called... (Tinawag po ang onPause())
10-02 16:58:51.084 32431-32431/com.cabatuan.lifecycleintroduction D/ActivityThread: ACT-AM_ON_PAUSE_CALLED ActivityRecord{42719368 token=android.os.BinderProxy@42718a28 {com.cabatuan.lifecycleintroduction/com.cabatuan.lifecycleintroduction.MainActivity}}
10-02 16:58:51.138 32431-32431/com.cabatuan.lifecycleintroduction D/ActivityThread: ACT-PAUSE_ACTIVITY_FINISHING handled : 0 / android.os.BinderProxy@42718a28
10-02 16:58:51.214 32431-32431/com.cabatuan.lifecycleintroduction D/OpenGLRenderer: Flushing caches (mode 0)
10-02 16:58:51.214 32431-32431/com.cabatuan.lifecycleintroduction D/GraphicBuffer: close handle(0x617737f8) (w:720 h:1280 f:1)
10-02 16:58:51.634 32431-32431/com.cabatuan.lifecycleintroduction D/OpenGLRenderer: Flushing caches (mode 1)
10-02 16:58:51.635 32431-32431/com.cabatuan.lifecycleintroduction D/MainActivity: onStop() method was called... (Tinawag po ang onStop())
10-02 16:58:51.635 32431-32431/com.cabatuan.lifecycleintroduction D/MainActivity: onDestroy() method was called... (Tinawag po ang onDestroy())
```


On relaunch after being destroyed:
```shell
10-02 17:01:33.158 32431-32431/com.cabatuan.lifecycleintroduction D/MainActivity: onCreate() method was called... (Tinawag po ang onCreate())
10-02 17:01:33.158 32431-32431/com.cabatuan.lifecycleintroduction D/MainActivity: onStart() method was called... (Tinawag po ang onStart())
10-02 17:01:33.158 32431-32431/com.cabatuan.lifecycleintroduction D/MainActivity: onResume() method was called... (Tinawag po ang onResume())
```


On configuration change (Rotating the Screen)
```shell
10-02 17:03:00.800 32431-32431/com.cabatuan.lifecycleintroduction D/MainActivity: onPause() method was called... (Tinawag po ang onPause())
10-02 17:03:00.800 32431-32431/com.cabatuan.lifecycleintroduction D/ActivityThread: ACT-AM_ON_PAUSE_CALLED ActivityRecord{42794250 token=android.os.BinderProxy@42793910 {com.cabatuan.lifecycleintroduction/com.cabatuan.lifecycleintroduction.MainActivity}}
10-02 17:03:00.801 32431-32431/com.cabatuan.lifecycleintroduction D/MainActivity: onSaveInstanceState() method was called... (Tinawag po ang onSaveInstanceState())
10-02 17:03:00.801 32431-32431/com.cabatuan.lifecycleintroduction D/MainActivity: onStop() method was called... (Tinawag po ang onStop())
10-02 17:03:00.801 32431-32431/com.cabatuan.lifecycleintroduction D/MainActivity: onDestroy() method was called... (Tinawag po ang onDestroy())
10-02 17:03:00.855 32431-32431/com.cabatuan.lifecycleintroduction D/OpenGLRenderer: Flushing caches (mode 0)
10-02 17:03:00.857 32431-32431/com.cabatuan.lifecycleintroduction D/GraphicBuffer: close handle(0x61778b50) (w:720 h:1280 f:1)
10-02 17:03:00.901 32431-32431/com.cabatuan.lifecycleintroduction D/MainActivity: onCreate() method was called... (Tinawag po ang onCreate())
10-02 17:03:00.901 32431-32431/com.cabatuan.lifecycleintroduction D/MainActivity: onStart() method was called... (Tinawag po ang onStart())
10-02 17:03:00.902 32431-32431/com.cabatuan.lifecycleintroduction D/MainActivity: onResume() method was called... (Tinawag po ang onResume())
```



## Submission Procedure with Git (sample): 

```shell
$ cd /path/to/your/android/app/
$ git init
$ git add –all
$ git commit -m "your message, e.x. Assignment 1 submission"
$ git remote add origin <Assignment link copied from assignment github, e.x. https://github.com/DeLaSalleUniversity-Manila/secondactivityassignment-melvincabatuan.git>
$ git push -u origin master
<then Enter Username and Password>
```

Ex. https://gist.github.com/melvincabatuan/aa6f1c2093fa524e86fd 


## Screenshots:

![alt tag](https://github.com/DeLaSalleUniversity-Manila/activitylifecycleintroduction-melvincabatuan/blob/master/2015-10-02-16:53:45.png)

![alt tag](https://github.com/DeLaSalleUniversity-Manila/activitylifecycleintroduction-melvincabatuan/blob/master/device-2015-10-02-170904.png)

![alt tag](https://github.com/DeLaSalleUniversity-Manila/activitylifecycleintroduction-melvincabatuan/blob/master/2015-10-02-17:06:23.png)

"Time is an illusion perpetrated by the manufacturers of space." - Anonymous
