## Directions

```
https://<your_instance_name>.syncano.space/google-maps/directions/
```

**Required parameters:**

`origin=[string]` - Address of start point

`destination=[string]` - Address of end point


**Optional parameters:**

`params=[object]` - Additional params can be found [here](https://developers.google.com/maps/documentation/directions/)

`mode=[string]` - one of driving | walking | bicycling | transit - driving is default mode

You will receive directions

**Example:**

```js
const directions = await endpoint.post('google-maps/directions',{
	"mode":"driving",
	"origin":"Brooklyn, New York, NY 1, USA",
	"destination":"Brooklyn, New York, NY 10009, USA"
})
```

Returned data is very detailed google directions data


## Distance


```
https://<your_instance_name>.syncano.space/google-maps/distance/
```

**Required parameters:**

`origin=[string]` - Address of start point

`destination=[string]` - Address of end point


**Optional parameters:**

`params=[object]` - Additional params can be found [here](https://developers.google.com/maps/documentation/directions/)

`mode=[string]` - one of driving | walking | bicycling | transit - driving is default mode

You will receive distance from origin to destination

**Example:**

```js
const distance = await endpoint.post('google-maps/distance',{
	"mode":"driving",
	"origin":"Brooklyn, New York, NY 1, USA",
	"destination":"Brooklyn, New York, NY 10009, USA"
})
```

Returned data value ( in meters! ):

```js
{
	"text": "24.9 mi",
	"value": 40052
}
```


## Time

```
https://<your_instance_name>.syncano.space/google-maps/time/
```

**Required parameters:**

`origin=[string]` - Address of start point

`destination=[string]` - Address of end point


**Optional parameters:**

`params=[object]` - Additional params can be found [here](https://developers.google.com/maps/documentation/directions/)

`mode=[string]` - one of driving | walking | bicycling | transit - driving is default mode

You will receive time from origin to destination

**Example:**

```js
const time = await endpoint.post('google-maps/time',{
	"mode":"driving",
	"origin":"Brooklyn, New York, NY 1, USA",
	"destination":"Brooklyn, New York, NY 10009, USA"
})
```

Returned data:

```js
{
	"text": "44 mins",
	"value": 2624
}
```
