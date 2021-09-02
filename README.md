# com.cabagomez-plugin.admobtapjoy
Tapjoy mediation support for Solar2d Admob Plugin   

To use:    
1. Add the plugin to your build settings like this:
```
["plugin_admobtapjoy"] = {
    publisherId = "com.cabagomez"
}
```
2. Add the following to application child settings. Make sure to change the store you are targeting:   
```
applicationChildElements =
    {
        ...
        [[
            <meta-data android:name="com.tapjoy.appstore" android:value="Amazon"/>
        ]],
        ...
    },
```
3. Set up your mediations and keys in the Admob portal.

Options calls you can make:   
```
local admobTapjoy = require( "plugin.admobtapjoy" )
admobTapjoy.setDebug(true) -- Or false.
admobTapjoy.setGcmSender() -- Have not tested this in a while. Suspect that it still works.
admobTapjoy.setUserLevel() -- Have not tested this in a while. Suspect that it still works.
admobTapjoy.setUserID( "fsdfsdf" )
admobTapjoy.setPrivacy( {
    underAge = true, 
    subjectToConsent = false, --subject to GDPR consent
    hasUserConsent = false -- required if subjectToConsent is true.
    } 
)
```