## Places

```
https://<your_instance_name>.syncano.space/google-maps/places/
```

**Required parameters:**

`keyword=[string]` - Location you are looking for

`location=[string]` - Location to seek around in correct google format

**Optional parameters:**

`params=[object]` - Additional params can be found [here](https://developers.google.com/places/web-service/search)

`radius=[integer]` - Radius to seek around location

You will receive array of possible places

**Example:**

```js

const places = await endpoint.post('google-maps/places',{
	location:"-33.8670522,151.1957362",
	radius:500,
	type:"restaurant"
})

```

Returned data is vast place array with each place details

## Place Photos


```
https://<your_instance_name>.syncano.space/google-maps/placePhotos/
```


**Required parameters:**

`keyword=[string]` - Location you are looking for


**Optional parameters:**

`params=[object]` - Additional params can be found [here](https://developers.google.com/places/web-service/query)

`radius=[integer]` - Radius to seek around location

`location=[string]` - Location to seek around in correct google format

`maxHeight=[integer]` - Maximum height of returned photo - default is off

`maxWidth=[integer]` - Maximum width of returned photo - default is 1000

You will receive array of photo urls

**Example:**

```js
const photos = await endpoint.post('google-maps/placePhotos',{
	keyword:"bacalar playa"
})
```

Returned data:

Where 'socket-development' is an instance name.

```js
[
	"https://socket-development.syncano.space/google-maps/placePhotoById/?photo=CmRaAAAA8TRvgho77EvIPRXgHA_LimqmLoq80CRj0sPoRYdVqWxt6PbE3nw9WgjededPWn-4LBw8u_RU4TE-vZTvWLem8wJGStVr4HEJ29o4J-tyeZMl3ft-HHgIkmoX_Q9ur7nqEhBqT6SiK9Rgr2dNUNcaB0cRGhTjfcU90lKIhtXz0xEfqRQAV3w_yw",
	"https://socket-development.syncano.space/google-maps/placePhotoById/?photo=CmRaAAAAnxhIFLTXq3Eiy48efFSoK4HYUvhkpNTcA3AxrBBJZXVoTsjxLz4fHxzpM3mvlMf2cpDCwQoo4a2EaxCuYRy_6YoPoPFxKM8bZxvumgC_oNyS77nOfBPQjoMExXRDwPwSEhAqpGgb2Qfx7WEoDi08el0LGhS-RGxJML-2WhuKfYE63lm90fCarQ",
	"https://socket-development.syncano.space/google-maps/placePhotoById/?photo=CmRZAAAAnikCmehNjJSlgHqMQXRVw66IAD0j6T-optI4DjxgFCTLXQJQv3nk-Hc5DtMZrWTaGXjy5omhtt9Nu5tWUid2XVdiPk4k-ArBN_J60lnhvTaqLQ-ieJMXshxAlWpwFj6PEhBnRCyhJFBdLCJV7Dfts4w_GhQKlJIjpidCSwYd9437hvNd-O761w",
	"https://socket-development.syncano.space/google-maps/placePhotoById/?photo=CmRaAAAA02poKVt_ShY49RvJ3hcJmSA4rNJ30PJmscYYnQHCvyYBVxE5K6YQm6tybPiIbs3Q2I1ppY0UMvyzUSIVbD-gdGwEKvYWvwOUnegoM9ezIB1WrVzDG_i0PknI1mwqA-4xEhAzyabHeV5yxJQINk4gtedZGhSbx2AfDZIHZ-jkPnviDqtkoz4fZw",
	"https://socket-development.syncano.space/google-maps/placePhotoById/?photo=CmRaAAAAdimx1jn56hIqjnJjq7ZErDKTA4a-pEzqfPmoMmWbFd8ph_PXZfOUqd8nC7L_h5I9BtF1-eTIIDHPd1EED7ZLNQqcvSyvIVrzEfJzcUGuUfDLJFr1syCo6TzI2ry2LIqBEhCXnCYSFPRxSIC27TVDxK94GhQLsoO2ITdGDqxhXi--fbuL4JQSNw",
	"https://socket-development.syncano.space/google-maps/placePhotoById/?photo=CmRaAAAAvBfNuAJwL-dEOiWbiZ34nZ12Kh2dfVnUS_0GPgjD-zu8hgnAJfmKoaDm9ZkHQN_xvTqO4MRm2MLMm11M6khtWSbDAP5WYNNmu1-5NrrStk0LxwT6y18ivYOdWKXfRdqlEhA5c7mC8L68j9WPQhu1CawSGhQpjOCBwkk0TrbvlYWYYYcvJh9Mig",
	"https://socket-development.syncano.space/google-maps/placePhotoById/?photo=CmRaAAAA18uU0xooOEdVtTy7JUqh2wDsy23ljks1i_MQOItbgzotpWvs04axQ133jBRnp6tQM1CoThfJkxTCHXnogaepdJj0pOQjbOR2diTIvfkhMzMwyfRokHOqfz4nfGLFGRp2EhACC3_e5ggML3LpmMC9UI8wGhR6S6Qd5jkvNFsrWRmsF0pK4gbFHA",
	"https://socket-development.syncano.space/google-maps/placePhotoById/?photo=CmRaAAAAvtnyx5h_toin0QzXzuCoQaTLzABbU5pYNqQZ7uk2XQhU0OzMakAdeURhctbF0crLuJUTcLP--anrhg18Of8PyvCcJnvEXbP77mMoSX9ublWRh_YlaoKE7kGrOpnOE2zIEhB0GmWqxtDVfDc5884XcBibGhRh9E1gXD4mw_LHqeqv9rBu-_iD6g",
	"https://socket-development.syncano.space/google-maps/placePhotoById/?photo=CmRaAAAAkKBy7itBeVipJVF-6qB8TmnFwiLQBBEUO_VX3WIHuOEG6TI_JiNOLt7OfAwA7gRm3tH79zd--2MST1lZs8bn7SyIw0fKsqHGs2SyG6R9n1w68E1ntU962Ea7aQpq3tDiEhAjGAWtc3P-DGZG3RFRjR5-GhSc5fbnTg_K2HF2uwj2JP6Z3GJWJQ",
	"https://socket-development.syncano.space/google-maps/placePhotoById/?photo=CmRaAAAAxVkVtTowg9W65yNxRT5ZB08sB2kEiTGFb6CseGc5INDLE_e1h0fz43cz-L6ifkQ-BcjOkgBh-nIY5y-TAWKdOWncUFzDcOP_KGQUkY3XW-CyUTF3shT3tihPOh0-8YViEhAwPHEsEZKWCv5tfc3QT4ZCGhQkGJc59ArH5o09tDLw1ZJJGA5VnA"
]
```


## Place Photo By Id

```
https://<your_instance_name>.syncano.space/google-maps/placePhotos/
```


**Required parameters:**

`photo=[string]` - Reference Id of photo

**Optional parameters:**

`maxHeight=[integer]` - Maximum height of returned photo - default is off

`maxWidth=[integer]` - Maximum width of returned photo - default is 1000

Returns place photo url


## Place Details

```
https://<your_instance_name>.syncano.space/google-maps/placeDetails/
```


**Required parameters:**

`placeId=[string]` - Reference Id of place

**Example:**

```js
const details = await endpoint.post('google-maps/placeDetails',{
	placeId:"ChIJCQn-GA_8H0cRctzV_krg-JU"
})
```

You will receive all place details. Since its a lot of them I won't present them here.