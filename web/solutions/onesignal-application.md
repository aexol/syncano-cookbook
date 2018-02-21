
# OneSignal App
---

For this operations you have to set `ONE_SIGNAL_USER_AUTH_KEY` in socket config.

## App details

```
https://<your_instance_name>.syncano.space/onesignal/view-app/
```

View details of your OneSignal app.

**Example:**
```js
const deviceData = await endpoint.post('onesignal/view-app', {})
```

Returned data:
```js
{
	"message": "Success getting app details",
	"response": {
		"id": "e6e1908b-f5db-437c-a109-f754e578dd9e",
		"name": "test app",
		"gcm_key": null,
		"chrome_key": null,
		"chrome_web_key": null,
		"chrome_web_origin": null,
		"chrome_web_gcm_sender_id": null,
		"chrome_web_default_notification_icon": null,
		"chrome_web_sub_domain": null,
		"apns_env": "production",
		"apns_certificates": "-----BEGIN CERTIFICATE ... END RSA PRIVATE KEY-----\n",
		"safari_apns_certificate": null,
		"safari_site_origin": null,
		"safari_push_id": null,
		"safari_icon_16_16": "public/safari_packages/e6e1908b-f5db-437c-a109-f754e578dd9e/icons/16x16.png",
		"safari_icon_32_32": "public/safari_packages/e6e1908b-f5db-437c-a109-f754e578dd9e/icons/16x16@2x.png",
		"safari_icon_64_64": "public/safari_packages/e6e1908b-f5db-437c-a109-f754e578dd9e/icons/32x32@2x.png",
		"safari_icon_128_128": "public/safari_packages/e6e1908b-f5db-437c-a109-f754e578dd9e/icons/128x128.png",
		"safari_icon_256_256": "public/safari_packages/e6e1908b-f5db-437c-a109-f754e578dd9e/icons/128x128@2x.png",
		"site_name": null,
		"created_at": "2018-02-16T10:47:04.545Z",
		"updated_at": "2018-02-20T10:40:47.509Z",
		"players": 1,
		"messageable_players": 1,
		"basic_auth_key": "auth key..."
	}
}
```
___

## All Apps details

```
https://<your_instance_name>.syncano.space/onesignal/view-apps/
```

View details of all your OneSignal apps.

**Example:**
```js
const deviceData = await endpoint.post('onesignal/view-apps', {})
```

Returned data:
```js
{
	"message": "Success getting apps details",
	"response": [
		{
  		"id": "e6e1908b-f5db-437c-a109-f754e578dd9e",
  		"name": "test app",
  		"gcm_key": null,
  		"chrome_key": null,
  		"chrome_web_key": null,
  		"chrome_web_origin": null,
  		"chrome_web_gcm_sender_id": null,
  		"chrome_web_default_notification_icon": null,
  		"chrome_web_sub_domain": null,
  		"apns_env": "production",
  		"apns_certificates": "-----BEGIN CERTIFICATE ... END RSA PRIVATE KEY-----\n",
  		"safari_apns_certificate": null,
  		"safari_site_origin": null,
  		"safari_push_id": null,
  		"safari_icon_16_16": "public/safari_packages/e6e1908b-f5db-437c-a109-f754e578dd9e/icons/16x16.png",
  		"safari_icon_32_32": "public/safari_packages/e6e1908b-f5db-437c-a109-f754e578dd9e/icons/16x16@2x.png",
  		"safari_icon_64_64": "public/safari_packages/e6e1908b-f5db-437c-a109-f754e578dd9e/icons/32x32@2x.png",
  		"safari_icon_128_128": "public/safari_packages/e6e1908b-f5db-437c-a109-f754e578dd9e/icons/128x128.png",
  		"safari_icon_256_256": "public/safari_packages/e6e1908b-f5db-437c-a109-f754e578dd9e/icons/128x128@2x.png",
  		"site_name": null,
  		"created_at": "2018-02-16T10:47:04.545Z",
  		"updated_at": "2018-02-20T10:40:47.509Z",
  		"players": 1,
  		"messageable_players": 1,
  		"basic_auth_key": "auth key..."
	  }
  ]
}
```
___
## Update app
```
https://<your_instance_name>.syncano.space/onesignal/update-app/
```

Updates your OneSignal app.

Parameter |  Type  | Description
--------- | ------ | -----------
name  | string | Application name

You can find more available parameters at [OneSignal documentation](https://documentation.onesignal.com/reference#update-an-app)

**Example:**
```js
const deviceData = await endpoint.post('onesignal/update-app', {
  name: "test new name"
})
```

Returned data:

```js
{
	"message": "Success updating app",
	"response": {
		"id": "e6e1908b-f5db-437c-a109-f754e578dd9e",
		"name": "test new name",
		"gcm_key": null,
		"chrome_key": null,
		"chrome_web_key": null,
		"chrome_web_origin": null,
		"chrome_web_gcm_sender_id": null,
		"chrome_web_default_notification_icon": null,
		"chrome_web_sub_domain": null,
		"apns_env": "production",
		"apns_certificates": "-----BEGIN CERTIFICATE ... END RSA PRIVATE KEY-----\n",
		"safari_apns_certificate": null,
		"safari_site_origin": null,
		"safari_push_id": null,
		"safari_icon_16_16": "public/safari_packages/e6e1908b-f5db-437c-a109-f754e578dd9e/icons/16x16.png",
		"safari_icon_32_32": "public/safari_packages/e6e1908b-f5db-437c-a109-f754e578dd9e/icons/16x16@2x.png",
		"safari_icon_64_64": "public/safari_packages/e6e1908b-f5db-437c-a109-f754e578dd9e/icons/32x32@2x.png",
		"safari_icon_128_128": "public/safari_packages/e6e1908b-f5db-437c-a109-f754e578dd9e/icons/128x128.png",
		"safari_icon_256_256": "public/safari_packages/e6e1908b-f5db-437c-a109-f754e578dd9e/icons/128x128@2x.png",
		"site_name": null,
		"created_at": "2018-02-16T10:47:04.545Z",
		"updated_at": "2018-02-20T10:40:47.509Z",
		"players": 1,
		"messageable_players": 1,
		"basic_auth_key": "auth key..."
	}
}
```
