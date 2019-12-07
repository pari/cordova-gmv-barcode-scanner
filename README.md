
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


