
## Address

```
https://<your_instance_name>.syncano.space/google-maps/address/
```

**Required parameters:**

`location=[string]` - Location to seek to perform inverse geolocation lookup

**Optional parameters:**

`params=[object]` - Additional params can be found [here](https://developers.google.com/maps/documentation/geocoding/start)

You will receive an address of place

**Example:**

```js
const address = await endpoint.post('google-maps/address',{
	location:"40.7084499,-73.9920949"
})
```

Returned data:

```js
{
	"formatted_address": "Manhattan Bridge Pedestrian Path, Brooklyn, NY 11201, USA"
}
```


## Geocoding

```
https://<your_instance_name>.syncano.space/google-maps/geocoding/
```

**Required parameters:**

`address=[string]` - Address to convert to location

or

`location=[string]` - Location to seek to perform inverse geolocation lookup

**Optional parameters:**

`params=[object]` - Additional params can be found [here](https://developers.google.com/maps/documentation/geocoding/start)

`radius=[integer]` - Radius to seek around location

You will receive array of possible locations

**Example:**

```js
const geocoding = await endpoint.post('google-maps/geocoding',{
	address:"Brooklyn Bridge",
	params:{
		language:"en",
		components:"country:us",
	}
})
```

Returned data:

```js
[
	{
		"address_components": [
			{
				"long_name": "Brooklyn Bridge",
				"short_name": "Brooklyn Bridge",
				"types": [
					"establishment",
					"point_of_interest"
				]
			},
			{
				"long_name": "Brooklyn Bridge",
				"short_name": "Brooklyn Bridge",
				"types": [
					"route"
				]
			},
			{
				"long_name": "Manhattan",
				"short_name": "Manhattan",
				"types": [
					"political",
					"sublocality",
					"sublocality_level_1"
				]
			},
			{
				"long_name": "New York",
				"short_name": "New York",
				"types": [
					"locality",
					"political"
				]
			},
			{
				"long_name": "New York County",
				"short_name": "New York County",
				"types": [
					"administrative_area_level_2",
					"political"
				]
			},
			{
				"long_name": "New York",
				"short_name": "NY",
				"types": [
					"administrative_area_level_1",
					"political"
				]
			},
			{
				"long_name": "United States",
				"short_name": "US",
				"types": [
					"country",
					"political"
				]
			},
			{
				"long_name": "10038",
				"short_name": "10038",
				"types": [
					"postal_code"
				]
			}
		],
		"formatted_address": "Brooklyn Bridge, New York, NY 10038, USA",
		"geometry": {
			"location": {
				"lat": 40.7060855,
				"lng": -73.9968643
			},
			"location_type": "GEOMETRIC_CENTER",
			"viewport": {
				"northeast": {
					"lat": 40.7084499,
					"lng": -73.9920949
				},
				"southwest": {
					"lat": 40.7031689,
					"lng": -73.99985219999999
				}
			}
		},
		"place_id": "ChIJK3vOQyNawokRXEa9errdJiU",
		"types": [
			"establishment",
			"point_of_interest"
		]
	}
]
```
