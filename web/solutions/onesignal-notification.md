
# Notification
---

## Create Notification

```
https://<your_instance_name>.syncano.space/onesignal/create-notification/
```

This endpoint allows you to create push notification programatically You may target users in one of three ways using this method: by **Segment**, by **Filter**, or by **Device**. At least one targeting parameter must be specified.

Parameters `app_id` and `REST KEY` filled from socket config, so you can omit them.

Parameter |  Type  | Description
--------- | ------ | -----------
contents  | object | **<font color="red"> REQUIRED </font>** unless `content_available=true` or `template_id` is set.<br/>Notification's content, a map of language codes to text for each language.<br/>**English must be included!**<br/>Example: ```{"en": "eglish message", "pl": "polska wiadomość"}```
headings | object | Notification's title. Has the same form as `contents`<br/>Example: ```{"en": "eglish message", "pl": "polska wiadomość"}```
subtitle | object | Notification's subtitle for **iOS 10+**. Has the same form as `contents`<br/>Example: ```{"en": "eglish message", "pl": "polska wiadomość"}```
template_id | string | Id of template defined in OneSignal Dashboard.<br/>Example: `be4a8044-bbd6-11e4-a581-000c2940e62c`
content_available | boolean | **iOS** If `true` then your app wakes from background to run custom native code.
Full documentation and all parameters that can be used are listed at [OneSignal Documentation](https://documentation.onesignal.com/reference#create-notification)

> ### ! You may only use one method of targeting users <br/>
> If a targeting parameter of one type is used, then targeting parameters from other types may not be used. For instance, you cannot use the `included_segments` parameter (from segments) with the `filters`.

### Segments {docsify-ignore}

Segments are the most common way developers send notifications via OneSignal. Sending to segments is easy: you simply specify which segments you want to send to, and, optionally, which ones you don't.

Parameter |  Type  | Description
--------- | ------ | -----------
`included_segments` | [string] | **<font color="red"> REQUIRED </font>** Users in these segments will receive a notification.<br/> **This targeting parameter is only compatible with `excluded_segments`**. <br/>Example: ```["All"]```
`excluded_segments` | [string] | Users in these segments will not receive a notification, even if they were included in `included_segments`.<br/> **This targeting parameter is only compatible with `included_segments`**. <br/>Example: ```["Active Users", "Inactive Users"]```

**Example:**
```js
const notification = await endpoint.post('onesignal/create-notification', {
  included_segments: ["All"],
  contents: {"en": "example content"}
})
```

### Filters {docsify-ignore}

You can filter users using many fields.

Parameter |  Type  | Description
--------- | ------ | -----------
`filters` | [object] | Array of filter objects. For more information visit [Filters Documentation](https://documentation.onesignal.com/reference#section-send-to-users-based-on-filters)

**Example:**
```js
const notification = await endpoint.post('onesignal/create-notification', {
  filters: [
    {"field": "tag", "key": "level", "relation": ">", "value": "10"},
    {"field": "amount_spent", "relation": ">","value": "0"}
  ],
  contents: {"en": "example content"}
})
```

### Specific Devices {docsify-ignore}

You can target specific users using their device ID.

Parameter |  Type  | Description
--------- | ------ | -----------
`include_player_ids` | [string] | Users from this array will receive notification<br/>Example: ```["fe3bcc9f-3289-4651-ad15-3b995718badd"]```<br/>**Array have limit 2000 entries per API call.**

**Example:**
```js
const notification = await endpoint.post('onesignal/create-notification', {
  include_player_ids:["fe3bcc9f-3289-4651-ad15-3b995718badd"],
  contents: {"en": "example content"}
})
```

Returned data:

```js
{
	"message": "push notification sent",
	"response": {
		"id": "0c7e8827-ffa3-44de-bce2-d8adb174ec3f",
		"recipients": 1
	}
}
```
___

## Cancel Notification

```
https://<your_instance_name>.syncano.space/onesignal/cancel-notification/
```

Endpoint stops scheduled or currently outgoing notification.

Parameter |  Type  | Description
--------- | ------ | -----------
`id` | [string] | **<font color="red"> REQUIRED </font>** Notification ID that you want to cancel

**Example:**
```js
const cancelNotification = await endpoint.post('onesignal/cancel-notification', {
  id: "bdd1aa9a-e1e2-4370-bef2-7fd501b87c0c",
})
```

Returned data:

```js
{
	"message": "notification cancelled",
	"response": {
		"success": true
	}
}
```
___

## View Notification

```
https://<your_instance_name>.syncano.space/onesignal/view-notification/
```

View single notification's details.

Parameter |  Type  | Description
--------- | ------ | -----------
`id` | [string] | **<font color="red"> REQUIRED </font>** Notification ID

**Example:**
```js
const notificationDetails = await endpoint.post('onesignal/view-notification', {
  id: "bdd1aa9a-e1e2-4370-bef2-7fd501b87c0c",
})
```

Returned data:

```js
{
	"message": "Success getting notification details",
	"response": {
		"adm_big_picture": "",
		"adm_group": "",
		"adm_group_message": {
			"en": ""
		},
		"adm_large_icon": "",
		"adm_small_icon": "",
		"adm_sound": "",
		"spoken_text": {},
		"alexa_ssml": null,
		"alexa_display_title": null,
		"amazon_background_data": false,
		"android_accent_color": "",
		"android_group": "",
		"android_group_message": {
			"en": ""
		},
		"android_led_color": "",
		"android_sound": "",
		"android_visibility": 1,
		"app_id": "e6e1908b-f5db-437c-a109-f754e578dd9e",
		"big_picture": "",
		"buttons": null,
		"canceled": true,
		"chrome_big_picture": "",
		"chrome_icon": "",
		"chrome_web_icon": "",
		"chrome_web_image": "",
		"chrome_web_badge": "",
		"content_available": false,
		"contents": {
			"en": "english message"
		},
		"converted": 0,
		"data": null,
		"delayed_option": "immediate",
		"delivery_time_of_day": "9:11AM",
		"errored": 0,
		"excluded_segments": [],
		"failed": 0,
		"firefox_icon": "",
		"headings": {
			"en": "english headings"
		},
		"id": "bdd1aa9a-e1e2-4370-bef2-7fd501b87c0c",
		"include_player_ids": null,
		"included_segments": [
			"All"
		],
		"ios_badgeCount": 1,
		"ios_badgeType": "None",
		"ios_category": "",
		"ios_sound": "",
		"apns_alert": {},
		"isAdm": false,
		"isAndroid": false,
		"isChrome": false,
		"isChromeWeb": false,
		"isAlexa": false,
		"isFirefox": false,
		"isIos": true,
		"isSafari": false,
		"isWP": false,
		"isWP_WNS": false,
		"large_icon": "",
		"priority": 5,
		"queued_at": 1519027894,
		"remaining": 1,
		"send_after": 1519035092,
		"small_icon": "",
		"successful": 0,
		"tags": null,
		"filters": null,
		"template_id": null,
		"ttl": null,
		"url": "",
		"web_buttons": null,
		"web_push_topic": null,
		"wp_sound": "",
		"wp_wns_sound": ""
	}
}
```
___
## View Notifications
```
https://<your_instance_name>.syncano.space/onesignal/view-notifications/
```

View details of multiple notifications.

Parameter |  Type  | Description
--------- | ------ | -----------
`limit` | string | How many notifications to return. Default is `50`
`offset` | string | Result offset. Default is `0`

> Notifications data older than 30 days are periodically deleted

**Example:**
```js
const notificationDetails = await endpoint.post('onesignal/view-notification', {
  id: "bdd1aa9a-e1e2-4370-bef2-7fd501b87c0c",
})
```

Returned data:

```js
{
	"message": "Success getting notification details",
	"response": {
		"total_count": 1,
		"offset": 0,
		"limit": 50,
		"notifications": [
			{
				"adm_big_picture": null,
				"adm_group": null,
				"adm_group_message": null,
				"adm_large_icon": null,
				"adm_small_icon": null,
				"adm_sound": null,
				"spoken_text": null,
				"alexa_ssml": null,
				"alexa_display_title": null,
				"amazon_background_data": null,
				"android_accent_color": null,
				"android_group": null,
				"android_group_message": null,
				"android_led_color": null,
				"android_sound": null,
				"android_visibility": null,
				"app_id": "e6e1908b-f5db-437c-a109-f754e578dd9e",
				"big_picture": null,
				"buttons": null,
				"canceled": false,
				"chrome_big_picture": null,
				"chrome_icon": null,
				"chrome_web_icon": null,
				"chrome_web_image": null,
				"chrome_web_badge": null,
				"content_available": null,
				"contents": {
					"en": "example content"
				},
				"converted": 0,
				"data": null,
				"delayed_option": null,
				"delivery_time_of_day": null,
				"errored": 0,
				"excluded_segments": [],
				"failed": 0,
				"firefox_icon": null,
				"headings": {},
				"id": "0c7e8827-ffa3-44de-bce2-d8adb174ec3f",
				"include_player_ids": [
					"fe3bcc9f-3289-4651-ad15-3b995718badd"
				],
				"included_segments": [],
				"ios_badgeCount": null,
				"ios_badgeType": null,
				"ios_category": null,
				"ios_sound": null,
				"apns_alert": null,
				"isAdm": false,
				"isAndroid": false,
				"isChrome": false,
				"isChromeWeb": false,
				"isAlexa": false,
				"isFirefox": false,
				"isIos": true,
				"isSafari": false,
				"isWP": false,
				"isWP_WNS": false,
				"large_icon": null,
				"priority": null,
				"queued_at": 1519139430,
				"remaining": 0,
				"send_after": 1519139430,
				"small_icon": null,
				"successful": 1,
				"tags": null,
				"filters": null,
				"template_id": null,
				"ttl": null,
				"url": null,
				"web_buttons": null,
				"web_push_topic": null,
				"wp_sound": null,
				"wp_wns_sound": null
			}
    ]
  }
}

```
