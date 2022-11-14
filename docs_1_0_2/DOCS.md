# ROSNInstant
Top level namespace for the Games SDK.

## initializeAsync()

Initializes the SDK library. This should be called before any other SDK functions.

**Examples**

```ts

ROSNInstant.initializeAsync().then(()=>{
  // Many properties will be null until the initialization completes.
  // This is a good place to fetch them:
  var sdkVersion = ROSNInstant.getSDKVersion(); // '1.0'
});
```
Returns Promise<void> that resolves when the SDK is ready to use.
___

### showAds

▸ **showAds**(`adsType`, `onSuccess`, `onFailure`): `void`

#### Parameters

| Name        | Type         | Description                 |
| :---------- | :----------- | :-------------------------- |
| `config`    | `AdsConfig`  | config ads                  |
| `onSuccess` | () => `void` | trigger on view ads success |
| `onFailure` | () => `void` | trigger on view ads failed  |

#### Returns

`void`

**Examples**

```ts
const config = { adsType: "reward", rewardType: "POINT", num: 9 };
ROSNInstant.showAds(
  config,
  (reward) => {
    console.log("view ads success", reward);
  },
  () => {
    console.log("view ads failed");
  }
)
```

## AdsConfig

Represents a config for ROSNInstant.showAds

Type: [Object][object]

**Properties**

 - `adsType` **string** type ads "reward" or "interstitial".
 - `rewardType` **string**  "POINT" or "SCORE"
-  `num` **number** score/point expectation

___

### closeGame
Indicates that the game has finished.
▸ **closeGame**(): `void`

#### Returns

`void`

___

## onPause()

Set a callback to be fired when a app background;

**Examples**

```ts

ROSNInstant.onPause(function() {
  console.log('app background was triggered');
})
 
```
Returns <void>
___

## onResume()

Set a callback to be fired when a app foreground;

**Examples**

```ts

ROSNInstant.onResume(function() {
  console.log('app foreground was triggered');
})
 
```
Returns <void>
___

## injectDebug()

inject console log runtime

**Examples**

```ts

ROSNInstant.injectDebug();
 
```
Returns <void>
___


## encryptKey()

Extra method, encrypt string

**Examples**

```ts
const key = "qwerty";
ROSNInstant.encryptKey(key); //U2FsdGVkX19BD+IVS1PCPNVkgBAdW1PPywa4mZ1mhbg=
 
```
Returns <string> key encrypted
___