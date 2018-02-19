## Suggest

```
https://<your_instance_name>.syncano.space/google-maps/suggest/
```

**Required parameters:**

`keyword=[string]` - suggestion keyword

**Optional parameters:**

`params=[object]` - Additional params can be found [here](https://developers.google.com/places/web-service/autocomplete)

You will receive an [array] of strings containing possible addresses

**Example:**

```js
const suggestions = await endpoint.post('google-maps/suggest',{
	keyword:"Wash",
	params:{
		language:"en",
	    components:"country:us"
	}
})
```

Returned data:

```js
[
	"Washington, DC, USA",
	"Washingtonian Boulevard, Gaithersburg, MD, USA",
	"Washington Boulevard, Arlington, VA, USA",
	"Washington Monument, Washington, DC, USA",
	"Washington National Cathedral, Washington, DC, USA"
]
```


## Place Query

```
https://<your_instance_name>.syncano.space/google-maps/placeQuery/
```


**Required parameters:**

`keyword=[string]` - Location you are looking for


**Optional parameters:**

`params=[object]` - Additional params can be found [here](https://developers.google.com/places/web-service/query)

`radius=[integer]` - Radius to seek around location

`location=[string]` - Location to seek around in correct google format

You will receive array of possible place suggesstions

**Example:**

```js
const places = await endpoint.post('google-maps/placeQuery',{
	keyword:"pizza near Springfield",
})
```

Returned data:

```js
[
	"pizza near Springfield, MO, USA",
	"pizza near Springfield, VA, USA",
	"pizza near Springfield, MA, USA",
	"pizza near Springfield, IL, USA",
	"pizza near Springfield, OR, USA"
]
```


## Place Autocomplete

```
https://<your_instance_name>.syncano.space/google-maps/placeAutocomplete/
```


**Required parameters:**

`keyword=[string]` - Location you are looking for


**Optional parameters:**

`params=[object]` - Additional params can be found [here](https://developers.google.com/places/web-service/query)

`radius=[integer]` - Radius to seek around location

`location=[string]` - Location to seek around in correct google format

You will receive array of possible place suggesstions

**Example:**

```js
const places = await endpoint.post('google-maps/placeAutocomplete',{
	keyword:"la siren warsaw poland",
})
```

Returned data:

```js
[
	{
		"description": "La Sirena: The Mexican Food Cartel, Piękna, Warsaw, Poland",
		"id": "791ab24305a20fe7d11b9ba8eb50aa1627ffa676",
		"matched_substrings": [
			{
				"length": 9,
				"offset": 0
			},
			{
				"length": 6,
				"offset": 44
			},
			{
				"length": 6,
				"offset": 52
			}
		],
		"place_id": "ChIJ2WAuj-7MHkcRuJN_GdwSfXs",
		"reference": "ClRJAAAAqga1tD9eqK6rEucEMVcXjCtzHkb4ASd-aJqEVqKiM4hC4WklJDE7_lyLCbf0Kxl1yy4hUB0onpxtvy1Y6NQ4UE2n2E0ukJCBOtMP3xG4z3ESEFp3GLJBwoeZgLbXAhM3CoAaFJTc_AcbXX4aFPYrHOjP-txCKspu",
		"structured_formatting": {
			"main_text": "La Sirena: The Mexican Food Cartel",
			"main_text_matched_substrings": [
				{
					"length": 9,
					"offset": 0
				}
			],
			"secondary_text": "Piękna, Warsaw, Poland",
			"secondary_text_matched_substrings": [
				{
					"length": 6,
					"offset": 8
				},
				{
					"length": 6,
					"offset": 16
				}
			]
		},
		"terms": [
			{
				"offset": 0,
				"value": "La Sirena: The Mexican Food Cartel"
			},
			{
				"offset": 36,
				"value": "Piękna"
			},
			{
				"offset": 44,
				"value": "Warsaw"
			},
			{
				"offset": 52,
				"value": "Poland"
			}
		],
		"types": [
			"establishment"
		]
	}
]
```