# About
Sigmon SDK Development for Simulator
<!--
<br/>
<br/>
To help you better understand how to install Sigmon SDK, please watch the video below
<br/>
https://www.youtube.com/watch?v=44bI5ev9ASk
</br>
<br/>
-->
<h2>Requirements</h2>
<ul>
<li>Mac OS Monterey 12.2.1</li>
<li>XCode 13.2.1</li>
<li>Swift 5.0</li>
</ul>
<h2>How To Install</h2>
<br/>
After donwloading SigmonSDK.framework, please open your project and then add SigmonSDK.framework to your project as shown below.
<br/>
<img src="https://raw.githubusercontent.com/maedilaziman/dev-ios-sigmonsdk/master/Screenshots/IMG_01.png" width="300" />
<br/>
Once you have successfully add SigmonSDK.framework, select the project in the Project navigator, and then open the General tab, look at 'Frameworks, Libraries, and Embedded Content',
<br/>
please choose Embed Without Signing in the SigmonSDK.framework as shown below.
<br/>
<img src="https://raw.githubusercontent.com/maedilaziman/dev-ios-sigmonsdk/master/Screenshots/IMG_02.png" width="300" />
<br/>
Select info.plist and add App Transport Security Settings until Privacy - Location When In Use Usage Description as shown below.
<br/>
<img src="https://raw.githubusercontent.com/maedilaziman/dev-ios-sigmonsdk/master/Screenshots/IMG_03.png" width="300" />
<br/>
You have successfully add SigmonSDK.framework to your project
<h2>How To Use</h2>
<br/>
Open your UIViewController class, then import SigmonSDK, in that class please implement protocol SMSDKMainSpeedTestComm and SMSDKMainSpeedTestSetCredentialComm as shown below.
<br/>
<img src="https://raw.githubusercontent.com/maedilaziman/dev-ios-sigmonsdk/master/Screenshots/IMG_04.png" width="300" />
This set credential key is mandatory, you can't fill empty credential key
<pre>
    <code>
	func setCredentialKey() -> String {
    	    return credentialKey
	}
   </code>
</pre>
Before you can test speed, SDK will return info whether set credential key was successful or not, 
if successful then the value of data.success = true,  
and if not then the value of data.success = false, and data.error will provide information 
about the error description
<pre>
    <code>
	func onCompleteSetCredentialKey(data: CredentialKeyData) {
    	    print("SDKTest_set_credential: \(data.success) ; Error: \(data.error)")
	}
   </code>
</pre>
<br/>
Declare SMSDKMainSpeedTestUI and SMSDKMainSpeedTestMainUI classes as shown below.
<br/>
<img src="https://raw.githubusercontent.com/maedilaziman/dev-ios-sigmonsdk/master/Screenshots/IMG_05.png" width="300" />
<br/>
Initialize SMSDKMainSpeedTestUI and SMSDKMainSpeedTestMainUI classes as shown below.
<br/>
<img src="https://raw.githubusercontent.com/maedilaziman/dev-ios-sigmonsdk/master/Screenshots/IMG_06.png" width="300" />
<br/>
After you have initialize SMSDKMainSpeedTestUI and SMSDKMainSpeedTestMainUI classes, you can add startSpeedTest() action in your event. Like the image below.
(startSpeedTest() method will return an empty string if there is no error message.)
<br/>
<img src="https://raw.githubusercontent.com/maedilaziman/dev-ios-sigmonsdk/master/Screenshots/IMG_07.png" width="300" />
<br/>
<b>Note:</b> before you access startSpeedTest() action, you must initialize SMSDKMainSpeedTestUI and SMSDKMainSpeedTestMainUI classes
<br/>