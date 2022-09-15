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

Returns Promise<void> that resolves when the SDK is ready to use.

```

### showRewardAds

▸ **showRewardAds**(`onSuccess`, `onFailure`): `void`

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `onSuccess` | () => `void` | trigger on view ads success |
| `onFailure` | () => `void` | trigger on view ads failed |

#### Returns

`void`

**Examples**

```ts
ROSNInstant.showRewardAds(
  () => {
    console.log("View ads success callback");
  },
  () => {
    console.log("View ads failed");
  }
);
```