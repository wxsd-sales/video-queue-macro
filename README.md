# Video Queue Macro

This is a Webex Device Macro which displays a video while waiting in a call queue. This demonstrates how additional content can be displayed on a Webex Device while a person is waiting for their call to be answered by an agent.

## Overview

This macro monitors which number a Webex Device is in a call with. Using this information, we can identify if a device is currently in a Webex Calling call queue by monitoring for the call queue extension number. Once detected, we can launch a WebView on the devices interface. This WebView can display any content you want to while the device waiting. In the example macro, we show an auto playing video playlist.

The macro also adds a speed dial button to your device. The target number which the button will dial can be anything but for this example we dial the same Webex Calling call queue extension.

Therefore, tapping the speed dial button will dial the call queue extension and then the macro will launch a WebView when it detects it is currently in a call with that queues extension.

The configuration blow is a snippet from the macro and shows how to create multiple speed dial buttons and specify multiple call queue extension to monitor and also different web based content to be displayed for each.

```js
const config = {
  buttons: [        // Array of buttons, will be auto added to the device
    {
      name: 'Call For Assistance',
      icon: 'Concierge',
      color: '#0000ff',
      target: '2222'
    }
    // Add your additional speed dial buttons here
  ],
  queues: [       // Array of queues to monitor and display commercials
    {
      title: 'Please wait 😊', // The title which is display when in modal mode
      number: '2222', // Number to monitor
      url: 'https://<your content url>,  // URL to display
      mode: 'Fullscreen',       // Fullscreen | Modal
      target: 'OSD'     // OSD | Controller
    }
    // Add your additional queue monitoring settings here
  ],
  hideUI: true, // true = hide out of call controls, false = show controls
  hideIncallUI: false,  // true = hide in call call controls, false = show controls
  panelId: 'call-queue',  // Our base Panel Id for all speed dial buttons
}
```


## Setup

### Prerequisites & Dependencies: 

- Webex Device running RoomOS 10.20.x or above.
- Device Web Admin or Control Hub access to enable and upload the Macro.


### Macro Installation Steps:
1. Download the ``video-queue.js`` file and upload it to your Webex Room device.
2. Configure the Macro by changing the initial values, there are comments explaining each one.
3. Enable the Macro.

### Webex Calling Call Queue Configuration:

This macro is intended to be used with a Webex Calling Call Queue as it is only this call flow in which the macro can detect it is waiting and has been answered by an agent. If the content you which to display while waiting has sound, it is recommended to disable the ringing tone and announcements on the Webex Calling Call Queue under  the Overflow Settings:

Control Hub -> Calling -> Features -> Call Queue -> (Your Call Queue) -> Overflow Settings 

![image](https://github.com/wxsd-sales/video-queue-macro/assets/21026209/aa5e2dca-37f3-4c0e-9534-3e37e6643423)



## Validation

Validated Hardware:

* Webex Room Kit Pro
* Webex Desk Pro
* Webex Desk Mini

  
## Demo

*For more demos & PoCs like this, check out our [Webex Labs site](https://collabtoolbox.cisco.com/webex-labs).


## License

All contents are licensed under the MIT license. Please see [license](LICENSE) for details.


## Disclaimer

Everything included is for demo and Proof of Concept purposes only. Use of the site is solely at your own risk. This site may contain links to third party content, which we do not warrant, endorse, or assume liability for. These demos are for Cisco Webex use cases, but are not Official Cisco Webex Branded demos.


## Questions
Please contact the WXSD team at [wxsd@external.cisco.com](mailto:wxsd@external.cisco.com?subject=video-queue-macro) for questions. Or, if you're a Cisco internal employee, reach out to us on the Webex App via our bot (globalexpert@webex.bot). In the "Engagement Type" field, choose the "API/SDK Proof of Concept Integration Development" option to make sure you reach our team. 


