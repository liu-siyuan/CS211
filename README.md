# CS211
Android app for VoLTE monitoring tool
This is the readme document for CS211, Spring 2015 project: Android app for VoLTE monitoring tool. You can know how to compile and run our code here.

Group: 		Siyuan Liu
			Fengjia Xiong
			Fuxing Liu
		
Advisor:	Professor S. Lu
Mentor:		Chi-Yu Li


I. Overview
		Our code contains two part: the C part and the Java part. Roughly speaking, the C part take charge of packet sniffering and pattern matching, and the Java part controls the application by creating the realtime execution process of the C binary file, and shows the result in Android application. You can see the detailed implementation from our ppt and report.


II. Compile
  	1. C part: 
		Our C program is located in the directory /C, called test.c. To test it, you may put it into a subdirectory of /sdcard of your android phone. It should be compiled inside C4droid, and the generated binary file is inside the C4droid execution path. Notice that this path is also the place where our output file is located, so it is critical for our program running correctly. In our test phone (the Samsung Galaxy S5 owned by Chi-Yu), this path is /data/data/com.n0n3m4.droidc/files/. It may differ from different version of C4droid, so you may change this path in Android program if our application does not work. 
		After compilation, the binary file is located in /data/data/com.n0n3m4.droidc/files/temp, and the output file is /data/data/com.n0n3m4.droidc/files/output.txt. Make sure you change the permission of output.txt to be READABLE & WRITABLE (777 is most prefered) so that our app can read from that file.
		
	2. Java part:
		After every configuration in last step, you should run our program successfully. If you encounter some problems in opening our Android project in Eclipse, try to use Android Studio to open it, because these two IDEs may not be compatible.
		Also, our major part is inside the class Monitor.java. It was called by DisplayActivity.java, and the inside details can be found in our ppt or report.
		
		
III. Environment setup
	1. Phones: 
		We use Chi-Yu's Galaxy S5 as our experiment phone. It is build on API18, Android 4.4.2 with root permission, and the carrier is Verizon. We strongly recommended you use the same phone to test our program, or at least one Verizon phone with VoLTE. This phone is as the caller in our project.
		The callee phone must be an AT&T phone, or the detected state may not be correct. Because all our analyses are based on the call from Verizon to AT&T, we strongly recommend you use the same two phones to test. This callee phone is owned by one of our group member Fengjia Xiong, number is (310)307-6483, If necessary, just feel free to call this number to test.
		
	2. Operations:
		In the main activity, you do not need to type any information. Just click SEND button, and you will go to display activity. Click START button to start monitoring, the pid of C program will appear if you grant it the root permission. To stop this program, you can either click the STOP button or wait for the program to return automatically, as long as the calling status can be determined.
		
	3. Results
		Our program can return 10 possible status. When the program stops automatically, you can see the status in both TextView and Toast. All the possible cases are:
		
		"The number does not exist."
		"The phone you are calling is no-signal status/ power off / airplane mode."
		"The phone you are calling decline."
		"No LTE."
		"I have cancelled the phone."
		"Airplane/ Shutdown."
		"Decline"
		"Success"
		"Finished"
		"Default"
		
		
		
		
