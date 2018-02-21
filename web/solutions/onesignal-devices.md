
# Devices
---

## View device

```
https://<your_instance_name>.syncano.space/onesignal/view-device/
```

View details of single device registered in your OneSignal app.

Parameter |  Type  | Description
--------- | ------ | -----------
id  | string | **<font color="red"> REQUIRED </font>** Player's OneSignal ID

**Example:**
```js
const deviceData = await endpoint.post('onesignal/view-device', {
  "id": "fe3bcc9f-3289-4651-ad15-3b995718badd"
})
```

Returned data:
```js
{
	"message": "view device success",
	"response": {
		"id": "fe3bcc9f-3289-4651-ad15-3b995718badd",
		"identifier": "cbc1e9eabf4f57469cb7d47a11468db39aa7a01d1dc154721475bd2737e2aac7",
		"session_count": 5,
		"language": "en",
		"timezone": 3600,
		"game_version": "1",
		"device_os": "11.2.1",
		"device_type": 0,
		"device_model": "iPhone6,2",
		"ad_id": "1AB34CA1-AA68-4B5E-82A3-0755C7614609",
		"tags": {},
		"last_active": 1519123419,
		"playtime": 120,
		"amount_spent": 2.97,
		"created_at": 1518782430,
		"invalid_identifier": false,
		"badge_count": 0,
		"sdk": "020700",
		"test_type": 1,
		"ip": "34.235.168.139"
	}
}
```
___
## View Devices

```
https://<your_instance_name>.syncano.space/onesignal/view-devices/
```

View details of multiple devices in your OneSignal app.

> ### ! Unavailable for Apps > 100,000 users
> For those apps use csv-export instead

**Example:**
```js
const deviceData = await endpoint.post('onesignal/view-devices', {})
```

Returned data:
```js
{
	"message": "view devices success",
	"response": {
		"total_count": 1,
		"offset": 0,
		"limit": 300,
		"players": [
			{
				"id": "fe3bcc9f-3289-4651-ad15-3b995718badd",
				"identifier": "cbc1e9eabf4f57469cb7d47a11468db39aa7a01d1dc154721475bd2737e2aac7",
				"session_count": 5,
				"language": "en",
				"timezone": 3600,
				"game_version": "1",
				"device_os": "11.2.1",
				"device_type": 0,
				"device_model": "iPhone6,2",
				"ad_id": "1AB34CA1-AA68-4B5E-82A3-0755C7614609",
				"tags": {},
				"last_active": 1519123419,
				"playtime": 120,
				"amount_spent": 2.97,
				"created_at": 1518782430,
				"invalid_identifier": false,
				"badge_count": 0,
				"sdk": "020700",
				"test_type": 1,
				"ip": "34.235.168.139"
			}
		]
	}
}
```
___
## CSV Export
```
https://<your_instance_name>.syncano.space/onesignal/csv-export/
```

Generate CSV file with your app's user data. Generating file may take several minutes depending on number of users.

**Example:**
```js
const deviceData = await endpoint.post('onesignal/csv-export', {})
```

Returned data:

```js
{
	"message": "Success generating csv file",
	"response": {
		"csv_file_url": "https://onesignal.s3.amazonaws.com/csv_exports/e6e1908b-f5db-437c-a109-f754e578dd9e/users_5798ed83c962cf2be88d2e8cf6175461_2018-02-21.csv.gz"
	}
}
```
