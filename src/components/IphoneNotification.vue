<template>
    <div
        :class="['vpnp-notification', appearanceModeClass, notificationExpandedClass]"
    >
        <div class="vpnp-notification-heading">
            <div class="vpnp-notification-heading-icon-name-container">
                <p
                    class="vpnp-notification-application-icon"
                    @click="toggleNotification"
                />

                <p
                    class="vpnp-notification-application-name"
                    v-html="textApplicationName"
                />
            </div>

            <p
                class="vpnp-notification-time"
                v-html="textTime"
            />
        </div>

        <div class="vpnp-notification-content">
            <div class="vpnp-notification-content-text">
                <p
                    v-if="hasTitle"
                    class="vpnp-notification-title"
                    v-html="textTitle"
                />

                <p
                    v-if="hasBody"
                    class="vpnp-notification-body"
                    v-html="textBody"
                />
            </div>

            <div
                v-if="hasImage"
                class="vpnp-notification-content-image"
                :style="[ notificationImageStyle ]"
            />
        </div>
    </div>
</template>

<script>
    import { deviceMixin } from '../mixins/deviceMixin';

    export default {
        name: 'IphoneNotification',

        mixins: [
            deviceMixin
        ],

        props: {
            textApplicationName: {
                type: String,
                default: 'App name'
            },

            textTime: {
                type: String,
                default: '1h ago',
                validator: value => value.length < 8
            },

            textTitle: {
                type: String,
                default: 'Title notification'
            },

            textBody: {
                type: String,
                default: ''
            },
        }
    }
</script>
