<template>
    <div class="navbar w-full flex items-center">
        <div class="flex w-full justify-between items-center">
            <h1 class="navbar__title">Platform Launch</h1>

            <div class="flex items-center">
                <button class="navbar__button" @click="openModal"><span class="mr-1">+</span>Add New Task</button>
            </div>
        </div>


        <addTaskComponent ref="addTaskModal"/>
    </div>
</template>

<script>
import addTaskComponent from '@/components/addTaskComponent.vue'

export default {
    name: 'navbarComponent',
    components: { addTaskComponent },

    data() {
        return {
            text: 'navbar',
            isModalOpen: false
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

        openModal() {
            this.$refs["addTaskModal"].open()
        }
    }
}
</script>

<style lang="scss">
.navbar {
    height: 10%;
    background-color: #2c2c38;
    border-bottom: 2px solid #393945;
    padding: 20px 25px;

    &__title {
        font-size: 24px;
        font-weight: 700;
        letter-spacing: 0.14rem;
    }

    &__button {
        background-color: #625fc6;
        color: #fff;
        padding: 6px 25px;
        border-radius: 30px;
        font-weight: 600;
        transition: .2s background-color;
        letter-spacing: 1px;
    }

    &__button:hover {
        background-color: #6b67d4;
    }

    &__button:active {
        background-color: #4e4ba1;
    }
}
</style>