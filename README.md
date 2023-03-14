# Video Queue Macro
Welcome to our WXSD DEMO Repo! <!-- Keep this here --> 

This is a Webex Device Macro which displays a video while waiting in a call queue


<!-- Keep the following here -->  
 *_Everything included is for demo and Proof of Concept purposes only. Your use of the site is solely at your own risk. This site may contain links to third party content, which we do not warrant, endorse, or assume liability for. These demos are for Cisco Webex usecases, but are not Official Cisco Webex Branded demos._
## Configuration

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

## Requirements

1. Webex Device running RoomOS 10.20.x or above.
2. Device Web Admin or Control Hub access to enable and upload the Macro.

## Setup

1. Download the ``video-queue.js`` file and upload it to your Webex Room device.
2. Configure the Macro by changing the initial values, there are comments explaining each one.
3. Enable the Macro.

## Validation

Validated Hardware:

* Webex Room Kit Pro
* Webex Desk Pro
* Webex Desk Mini

## Support

Please reach out to the WXSD team at [wxsd@external.cisco.com](mailto:wxsd@external.cisco.com?subject=video-queue-macro)
