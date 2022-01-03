# SoC - Blinky

Justin Reina

• [SoC - Blinky](file:///C:/Sw/SiliconLabs/SimplicityStudio/v5/developer/sdks/gecko_sdk_suite/v3.2/app/bluetooth/documentation/example/soc_blinky/readme.html "Getting started")


### Summary

This example implements a simple custom GATT service with two characteristics. One characteristic controls the state of the LED (ON/OFF) via write operations from a GATT client, and the second characteristic will send notifications to subscribed clients when the button state changes (pressed or released).

GATT Service:

- char1: LED state   (ON/OFF)

- char2: notification (button press)

## Procedure

@src soc_blinky/readme.html

```

	1. Launcher -> Thunderboard EFR32BG22 (BRD4184A RevA02)
	
	2. Create -> 'Bluetooth - SoC Blinky'
	
		'Link sdk and copy project contents' (#F21D)
		
		Build & Run project
	
	1. Install the [App](https://apps.apple.com/us/app/efr-connect/id1030932759)
	
	2. Open App -> Blinky
	
	3. Select -> Blinky Example
	
```

## App - Bluetooth - SoC Blinky

The classic blinky example using Bluetooth communication. From the EFR Connect mobile app, the LED controller button toggles LED0 on the board. In addition, on the board pressing or releasing BTN0 notifies the app. This is a demonstration of a simple two-way data exchange over GATT.

## Code Highlights

```

	1. Toggle LED
	
	app.c: sl_bt_on_event(): "if (data_recv == 0x00)" ("// Toggle LED.")
	
	2. Button Response
	
	app,cL: app_process_action(): update/send_report_button_characteristic()
```

# Test

```

	1. Pressing light bulb in app illuminates LED0
	
	2. Tap of BTN0 illuminates the button icon
	
```

## Results

```

	1. #DBB1: PASS
	2. #50DB: PASS

```

# References

```
    1. [QSG169: Bluetooth® SDK v3.x Quick Start Guide](https://www.silabs.com/documents/public/quick-start-guides/qsg169-bluetooth-sdk-v3x-quick-start-guide.pdf)
	2. [GATT Server and Client Roles](https://docs.silabs.com/bluetooth/latest/general/gatt-protocol/gatt-server-and-client-roles)

```
