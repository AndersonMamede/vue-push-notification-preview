# vue-push-notification-preview <a href="https://npm.im/vue-push-notification-preview"><img src="https://badgen.net/npm/v/vue-push-notification-preview"></a>

A library for previewing push notification on devices.

<a href="https://nenadjovanoski.github.io/vue-push-notification-preview/"><img src="/public/examples/main_example.png" alt="vue-push-notification-preview main example" /></a>

## 🙋‍♂️ Features
- **✅ No dependencies**
- **Android Device Preview**
- **iOS Device Preview**
- **🔥 Dark / Light mode notifications**

## 🚀 Install
```sh
npm i vue-push-notification-preview
```

## 🚦 Quick Setup

#### Register globally
Make it available anywhere in your Vue application.

```js
import { AndroidPreview, IphonePreview } from 'vue-push-notification-preview';

Vue.component('AndroidPreview', AndroidPreview);
Vue.component('IphonePreview', IphonePreview);
```

#### Register locally
Explicitly register it to a component you want to use it in.

```vue
<script>
  import { AndroidPreview, IphonePreview } from 'vue-push-notification-preview';

  export default {
    components: {
      AndroidPreview,
      IphonePreview
    },
    ...
};
</script>
```

### 👨🏻‍🏫 Documentation

Visit: https://nenadjovanoski.github.io/vue-push-notification-preview/

#### Props

All props for `AndroidPreview` and `IphonePreview` components:

| Name                      | Type      | Default                       | Description |
| ---                       | ---       | ---                           | ---         |
| textApplicationName       | String    | 'App name'                    |  |
| textTime                  | String    | '1h ago'                      |  |
| textTitle **(Android)**   | String    | ''                            |  |
| textTitle **(Iphone)**    | String    | 'Title notification'          |  |
| textBody                  | String    | ''                            |  |
| appearanceMode            | String    | 'light'                       | `'light'` and `dark` are possible options. |
| backgroundImage           | String    | ''                            | `backgroundImage` has lower priority over `backgroundColor`. |
| backgroundColor           | String    | '#c1c1c1'                     | `backgroundColor` has higher priority over `backgroundImage`. |
| height **(Android)**      | Number    | 644 and above (Recommended)   | Device `height` in pixels. The width gets calculated to keep device's ratio. |
| height **(Iphone)**       | Number    | 614 and above (Recommended)   | Device `height` in pixels. The width gets calculated to keep device's ratio. |


#### Events

All custom events for `AndroidPreview` and `IphonePreview` components:

| Name                                  | Trigger   | Description                                   |
| ---                                   | ---       | ---                                           |
| toggle-notification **(Android)**     | Click     | Click on **top right arrow** of notification  |
| toggle-notification **(Iphone)**      | Click     | Click on **application icon** of notification |


#### Slots

All named slots for `AndroidPreview` and `IphonePreview` components:


| Name      | Trigger   | Description                                   |
| ---       | ---       | ---                                           |
| header    | Click     | Click on **top right arrow** of notification  |
