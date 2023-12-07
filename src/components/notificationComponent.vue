<template>
    <a-button type="primary" @click="openNotification">Open the notification box</a-button>
</template>   

<script setup>
    import { SmileOutlined } from '@ant-design/icons-vue';
    import { notification } from 'ant-design-vue';
    import { h } from 'vue'


    const openNotification = () => {
        notification.open({
            message: 'Notification title',
            description: 'Moem garaje',
            icon: () => h(SmileOutlined, {style: 'color: #108ee9'})
        })
    }
</script>