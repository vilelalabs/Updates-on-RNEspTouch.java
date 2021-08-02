# Updates on RNEspTouch.java

This is an particular update on  RNEsptouchModule.java file from the project from [@liuminghui2017](https://github.com/liuminghui2017/react-native-esptouch)

Here I fix the known problem:

* attempt to invoke virtual method int android content.Context.checkPermission(java.lang.String, int, int) on a null object reference

Add add some new funcionalities to **getNetInfo** API:

* **res.ip** -> returns the ip of the divice using the App (not the ESP IP!)
* **res.ipPrefix** -> returns the same ip above, without the last octet

## Usage example in Java Script code for React Native

```js
function getInfo( async()=> {
  const { ip, ipPrefix } = await RNEsptouch.getNetInfo();
   console.log("ip:", ip);
   console.log("ipPrefix:", ipPrefix);
})

```

*There's more...* there are two additional "support" functions inside this .java file:
1) to convert int IP to String IP address
2) to split and join this IP to get the Prefix.


**PS**:  the ssid and bssid info from **getNetInfo()** will still work normally.
