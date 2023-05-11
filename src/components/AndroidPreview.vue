<template>
    <div
        :class="['vpnp-wrapper-pixel_4']"
        :style="[backgroundStyle, sizeStyle]"
    >
        <div class="vpnp-pixel_4">
            <div class="vpnp-content">
                <div class="vpnp-header">
                    <slot name="header"></slot>
                </div>

                <android-notification v-for="(notification, index) in notifications" :key="index" v-bind="notification"/>
            </div>
        </div>
    </div>
</template>

<script>
    import { DEVICE_SIZE } from '../constants/shared';

    import { deviceMixin } from '../mixins/deviceMixin';

    import AndroidNotification from './AndroidNotification';

    export default {
        name: 'AndroidPreview',

        components: {
            AndroidNotification
        },

        mixins: [
            deviceMixin
        ],

        props: {
            height: {
                type: Number,
                default: DEVICE_SIZE.PIXEL_4_HEIGHT
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
                    width: `${this.height * (DEVICE_SIZE.PIXEL_4_WIDTH / DEVICE_SIZE.PIXEL_4_HEIGHT)}px`
                }
            },
        }
    }
</script>
