<template>
    <Modal 
        class="taskModal" 
        :title="isEdit" 
        :open="isModalOpen" 
        :onOk="handleOk" 
        :onCancel="handleCancel"
    ></Modal>
</template>

<script>
import { Modal } from 'ant-design-vue';

export default {
    name: 'addTaskComponent',
    components: { Modal },

    data() {
        return {
            isModalOpen: false,
            isEditingTask: false
        }
    },

    methods: {
        handleOk() {
            this.isModalOpen = false
            alert('ok')
        },

        handleCancel() {
            this.isModalOpen = false
            alert('cancel')
        },

        open() {
            this.isModalOpen = true
        }
    },

    computed: {
        isEdit() {
            return this.isEditingTask ? 'Edit task' : 'Add new task'
        }
    }
}
</script>
<style>
.taskModal .ant-modal-content,
.taskModal .ant-modal-title {
    background-color: #2c2c38;
}

.taskModal .ant-modal-title {
    color: #fff;
    font-weight: 500;
    font-size: 22px;
}
</style>
