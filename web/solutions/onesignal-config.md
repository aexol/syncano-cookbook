## Onesignal Configuration

- Preparation: **5 minutes**
- Requirements:
  - Initiated Syncano project
  - Initiated One Signal Application at [OneSignal](https://onesignal.com/)
  - ONE_SIGNAL_REST_API_KEY
  - ONE_SIGNAL_APP_ID
  - ONE_SIGNAL_USER_AUTH_KEY (optional, required for some endpoints with administrator actions)
- Sockets:
  - [onesignal](https://syncano.io/#/sockets/onesignal)

## Installing dependencies

To install `onesignal` type:
```sh
$ syncano-cli add onesignal
$ syncano-cli deploy
```

You will be prompted to enter required config API KEYS: `ONE_SIGNAL_APP_ID` and `ONE_SIGNAL_REST_API_KEY`

## Configure API KEYS

To configure all config `API KEYS` type:
```sh
$ syncano-cli config onesignal
```

or to set each field separately type:
```sh
$ syncano-cli config-set onesignal <key_name> <value>
```
where `key_name` can be: `ONE_SIGNAL_REST_API_KEY`, `ONE_SIGNAL_APP_ID`, `ONE_SIGNAL_USER_AUTH_KEY`.

##### ONE_SIGNAL_REST_API_KEY
REST API KEY of your One Signal Application. Can be found in application dashboard at [onesignal](https://onesignal.com/)

##### ONE_SIGNAL_APP_ID
APP ID of your One Signal Application. Can be found in application dashboard at [onesignal](https://onesignal.com/)

More information can be found at [account-and-keys](https://documentation.onesignal.com/docs/accounts-and-keys)

##### ONE_SIGNAL_USER_AUTH_KEY
USER AUTH KEY of applications administrator.

More information can be found at [account](https://documentation.onesignal.com/docs/account)
