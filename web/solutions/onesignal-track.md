
# Track
---

## New session

```
https://<your_instance_name>.syncano.space/onesignal/new-session/
```

Update device's session information.
This will increment the player's `session_count`.

Parameter |  Type  | Description
--------- | ------ | -----------
player_id  | string | **<font color="red"> REQUIRED </font>** Player's OneSignal ID
sessionData | object | Session body parameters. More info at [OneSignal Documentation](https://documentation.onesignal.com/reference#new-session)

**Example:**
```js
const notification = await endpoint.post('onesignal/new-session', {
  "player_id": "fe3bcc9f-3289-4651-ad15-3b995718badd"
})
```

Returned data:
```js
{
	"message": "session updated",
	"response": {
		"success": true
	}
}
```
___

## New purchase

```
https://<your_instance_name>.syncano.space/onesignal/new-purchase/
```

Track new purchase in your app.
This will increment the player's `amount_spent`.

Parameter |  Type  | Description
--------- | ------ | -----------
player_id  | string | **<font color="red"> REQUIRED </font>** Player's OneSignal ID
purchaseData | object | Purchase body parameters. Required fields can be found at [OneSignal Documentation](https://documentation.onesignal.com/reference#new-purchase)

**Example:**
```js
const notification = await endpoint.post('onesignal/new-purchase', {
  "player_id": "fe3bcc9f-3289-4651-ad15-3b995718badd",
	"purchaseData": {"purchases": [{"sku": "SKU123", "iso": "USD", "amount": "0.99"}]}
})
```

Returned data:
```js
{
	"message": "new purchase added",
	"response": {
		"success": true
	}
}
```

___

## Increment session length

```
https://<your_instance_name>.syncano.space/onesignal/increment-session-length/
```

Update a device's session length upon app resuming

Parameter |  Type  | Description
--------- | ------ | -----------
player_id  | string | **<font color="red"> REQUIRED </font>** Player's OneSignal ID
state | string | **<font color="red"> REQUIRED </font>** set to `"ping"`
active_time | integer | **<font color="red"> REQUIRED </font>** The lesser of: The number of seconds since either: 1. `on_focus` was last called OR 2. `on_session` or the device first registered

**Example:**
```js
const notification = await endpoint.post('onesignal/increment-session-length', {
	"player_id": "fe3bcc9f-3289-4651-ad15-3b995718badd",
	"state": "ping",
	"active_time": 60
})
```

Returned data:
```js
{
	"message": "increment session success",
	"response": {
		"success": true
	}
}
```
___

## Track open

```
https://<your_instance_name>.syncano.space/onesignal/track-open/
```

Track when users open a notification

Parameter |  Type  | Description
--------- | ------ | -----------
id  | string | **<font color="red"> REQUIRED </font>** Notification ID
opened | boolean | **<font color="red"> REQUIRED </font>** set to `"true"`

**Example:**
```js
const notification = await endpoint.post('onesignal/track-open', {
	"id": "f84e3ac6-399e-43b7-90fa-ea0fff0668bf",
	"opened": true
})
```

Returned data:
```js
{
	"message": "track open success",
	"response": {
		"success": true
	}
}
```
