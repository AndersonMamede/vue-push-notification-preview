<template>
    <div
        :class="['vpnp-wrapper-iphone_x']"
        :style="[backgroundStyle, sizeStyle]"
    >
        <div class="vpnp-iphone_x">
            <div class="vpnp-content">
                <div
                    class="vpnp-header"
                >
                    <slot name="header"></slot>
                </div>

                <iphone-notification v-for="(notification, index) in notifications" :key="index" v-bind="notification"/>
            </div>
        </div>
    </div>
</template>

<script>
    import { DEVICE_SIZE } from '../constants/shared';

    import { deviceMixin } from '../mixins/deviceMixin';

    import IphoneNotification from './IphoneNotification';

    export default {
        name: 'IphonePreview',

        components: {
            IphoneNotification
        },

        mixins: [
            deviceMixin
        ],

        props: {
            height: {
                type: Number,
                default: DEVICE_SIZE.IPHONE_X_HEIGHT
            },
            notifications: {
                type: Array,
                default: () => [
                    { textApplicationName: 'App name' }
                ]
            },
        },

        computed: {
            sizeStyle() {
                return {
                    height: `${this.height}px`,
                    width: `${this.height * (DEVICE_SIZE.IPHONE_X_WIDTH / DEVICE_SIZE.IPHONE_X_HEIGHT)}px`
                }
            },
        }
    }
</script>
