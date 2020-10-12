** THIS IS RATHER OUTDATED STUFF and sometimes gives wrong scans **


Instead you should be Use https://github.com/Ratsoc/cordova-plugin-firebase-ml-kit-barcode-scanner


cordova-gmv-barcode-scanner
===========================

Clone (with my modifications) of https://github.com/dealrinc/cordova-gmv-barcode-scanner

Installation
------------

````
cordova plugin add https://github.com/pari/cordova-gmv-barcode-scanner
````

Usage
-----

### Plugin Options

The default options are shown below. Note that the `detectorSize.width` and `detectorSize.height` values must be floats. If the values are greater than 1 then they will not be visible on the screen. Use them as decimal percentages to determine how large you want the scan area to be.
````javascript
var options = {
	types: {
		Code128: true,
		Code39: true,
		Code93: true,
		CodaBar: true,
		DataMatrix: true,
		EAN13: true,
		EAN8: true,
		ITF: true,
		QRCode: true,
		UPCA: true,
		UPCE: true,
		PDF417: true,
		Aztec: true
	},
	detectorSize: {
		width: .5,
		height: .7
	},
	displayString: "",
        scanMode : 0 , // 0 for single scan , 1 for continuous 
        allowDuplicates : 0 // this variable applies only for continuous mode , 
            // 0 for do not allow duplicates , 1 for allow duplicates 
}


window.plugins.GMVBarcodeScanner.scan( options , function(err, result) { 
    
	//Handle Errors
	if(err) return;
	
	//Do something with the data.
	alert(result);
});


````

Note: While making changes to android code of the plugin , 
      the build process copies the plugin in many places - 
      
      You should be working in the folder :
      $YOUR_PROJECT/platforms/android/app/src/main/java/com/dealrinc/gmvScanner/
      
      The UI is in the folder 
      $YOUR_PROJECT/platforms/android/app/src/main/res/layout/barcode_capture.xml
      
      AND NOT the following folders
      $PROJECT/node_modules/cordova-gmv-barcode-scanner/src/android/src/gmvScanner/
      $PROJECT/plugins/cordova-gmv-barcode-scanner/src/android/src/gmvScanner/

      Once you have finalized your changes to the Source - commit the diff to this code base
      
      adb logcat | grep TESTGMV
      
