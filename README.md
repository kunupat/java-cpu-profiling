# Java Application CPU Profiling
How to do Java Application's CPU Profiling using Java VisualVM

## Using Java VisualVM For CPU Profiling

Path of Java VisualVM- `<JAVA_HOME>/bin/jvisualvm.exe`

### Java VisualVM - Install Profiler Plugin
Open Java VisualVM and make sure to install Profiler Plugin from the `Available Plugins` tab. Once installed, The plugin should be listed in the `Installed` tab as shown in below screenshot-
![Java VisualVM Profiler Plugin](Java_VisualVM_Profiler_Plugin_Installation.png?raw=true "Java VisualVM Profiler Plugin")


### Java VisualVM Settings
Now open the `Profile Startup` setting window from the `Application` -> `Profile Startup` menu. 

Things to note-
* Use an available port number on your system for attaching the profiler to your app to be profiled
* `Start Profiling From Classes` section should your application classes or packages

![Java VisualVM Settings](Java_VisualVM_Settings.png?raw=true "Java VisualVM Settings")

Now copy the generated JVM parameters by clicking on `Copy to Clipboard` button.


### Starting the Application By Enabling Profiling

Now go to Eclipse Run Configurations and paste the copied JVM arguments to the `VM Arguments` section as shown below; save and run the app.

![Running app with profiling from Eclipse](Java_Profiling_Running_The_App.png?raw=true "Running app with profiling from Eclipse")

If you get the error code 62, then do this-

```
CPU Profiling Fails With "Redefinition failed with error 62"
Resolution: Restart the application with the VM argument -Xverify:none to disable classfile verification. 
```

### Profiling Results

After this app run terminates, you would be prompted by Java VisualVM to save the snapshot of this run. Save the snapshot and view it by selecting it. This should look as shown below-

![Profiling Results](Java_Profiling_Results.png?raw=true "Profiling Results")

Now you can see how much time was spent in each of the methods in the call tree.

## Important Note
It is advised that you *don't* run profiling in production and other higher version as byte code instrumentation has some overhead. So, care must be taken to run profiling on your development workspace only.

## Memory Profiling

This profiler can be used to do memory profiling as well simply by selecting `Memory` profiling while setting Application Profile options.



