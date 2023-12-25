<template>
    <Modal 
        class="taskModal" 
        :title="isEdit" 
        :open="isModalOpen" 
        :onOk="handleOk" 
        okText="Create task"
        :onCancel="handleCancel"
        :okButtonProps="{class: 'addTaskModal'}"
        :cancelButtonProps="{style: {display: 'none'}}"
    >
        <div class="flex flex-col">
            <label class="text-white tracking-wider">Title</label>
            <a-input class="modalInput placeholder-gray-500" :count="{show: true, max: 10}" placeholder="e.g. Take coffee break" />
        </div>
        <div class="mt-3 flex flex-col">
            <label class="text-white tracking-wider">Description</label>
            <textarea rows="4" class="modalTextarea">At w3schools.com you will learn how to make a website. They offer free tutorials in all web development technologies.</textarea>
        </div>

        <div class="mt-4 flex flex-col">
            <label class="text-white tracking-wider">Subtasks</label>
            <div class="flex items-center mt-2">
                <input type="text" class="modalInput placeholder-gray-500 w-11/12 mr-4" placeholder="e.g. Make coffee">
                <CloseOutlined class="cursor-pointer" style="color: #838c9d;"/>
            </div>
            <div class="flex items-center mt-2">
                <input type="text" class="modalInput placeholder-gray-500 w-11/12 mr-4" placeholder="e.g. Drink coffee & smile">
                <CloseOutlined class="cursor-pointer" style="color: #838c9d;"/>
            </div>

            <Button class="mt-3 addNewSubtask" block><span>+</span> Add new subtask</Button>
        </div>

        <div class="mt-4">
            <label class="text-white tracking-wider">Status</label>
            <a-select
                v-model="value"
                class="modalSelect"
                show-search
                placeholder="Select a person"
                style="width: 100%"
                :options="options"
            ></a-select>
        </div>
    </Modal>
</template>

<script>
import { Modal, Button } from 'ant-design-vue';
import { CloseOutlined } from '@ant-design/icons-vue';

export default {
    name: 'addTaskComponent',
    components: { Modal, CloseOutlined, Button },

    data() {
        return {
            isModalOpen: false,
            isEditingTask: false,
            value: null,
            options: [ 
                { value: 'jack', label: 'Jack' },
                { value: 'lucy', label: 'Lucy' },
                { value: 'tom', label: 'Tom' },
            ]
        }
    },

    methods: {
        handleOk() {
            this.isModalOpen = false
            // alert('ok')
        },

        handleCancel() {
            this.isModalOpen = false
            // alert('cancel')
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

.addTaskModal {
    background-color: #645fc6 !important;
    color: #fff;
    border-radius: 20px;
    width: 100% !important;
    margin-left: 0px !important;
    font-size: 16px;
    font-weight: 500;
    height: auto;
}

.modalTextarea,
.modalInput {
    background-color: #2c2c38;
    border: 1px solid #393945;
    padding: 5px 13px;
    color: #fff;
    border-radius: 6px;
    transition: all 0.2s;
    outline: none !important;
}

.modalTextarea:hover,
.modalTextarea:active,
.modalTextarea:focus,
.modalInput:hover,
.modalInput:active,
.modalInput:focus {
    border: 1px solid #4096ff;
}

.addNewSubtask {
    background-color: #fff !important;
    color: #645fc6 !important;
    border-radius: 20px;
    font-weight: 500;
}

.addNewSubtask:focus,
.addNewSubtask:hover {
    background-color: #fff !important;
    color: #645fc6 !important;
    box-shadow: none;
    border: none;
    outline: none;
}

.modalSelect .ant-select-selector{
    background-color: #2c2c38 !important;
    border: 1px solid #393945 !important;
    border-radius: 6px;
    transition: all 0.2s;
}
.modalSelect .ant-select-selection-placeholder {
    color: #686e7c;
}

.modalSelect .ant-select-selection-item,
.modalSelect .ant-select-selection-item-remove,
.modalSelect .ant-select-selection-overflow {
    color: #fff;
}

.modalSelect .ant-select-selection-item-remove {
    display: flex;
}

.ant-modal-close-icon svg {
    color: #fff;
}
</style>
