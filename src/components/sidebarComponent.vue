<template>
    <div class="sidebar">
        <h1 class="sidebar__title">Kanban</h1>

        <div class="sidebar__boards">
            <span class="sidebar__boards--head">All boards({{ boardsList.length }})</span>

            <div class="flex items-center sidebar__board" v-for="text in boardsList">
                <AppstoreOutlined style="font-size: 20px; margin: 2px 10px 2px 0px; padding: 10px 0;" />
                <span class="text-xl">{{ text }}</span>
            </div>


            <div class="flex items-center sidebar__board">
                <AppstoreAddOutlined style="font-size: 20px; margin: 2px 10px 2px 0px; padding: 10px 0;" />
                <span class="text-xl"><span>+</span>Create new board</span>
            </div>
        </div>
    </div>
</template>

<script>
import { AppstoreOutlined, AppstoreAddOutlined } from '@ant-design/icons-vue';

export default {
    name: 'sidebarComponent',
    data() {
        return {
            boardsList: ['Platform launch', 'Marketing plan', 'Roadmap']
        }
    },

    components: {
        AppstoreOutlined,
        AppstoreAddOutlined
    }
}
</script>

<style lang="scss">
.sidebar {
    width: 20%;
    background-color: #2c2c38;
    min-height: 100vh;
    border-right: 2px solid #393945;
    padding: 15px 0 0 35px;
    position: relative;

    &__title {
        font-size: 36px;
        font-weight: 800;
    }

    &__boards {
        margin-top: 30px;

        &--head {
            font-size: 14px;
            font-weight: 600;
            letter-spacing: 3px;
            text-transform: uppercase;
            color: #6e7482;
        }
    }

    &__board {
        padding: 2px 0;
        cursor: pointer;
        background-color: blue;
        position: relative;
        z-index: 1;
    }

    &__board::after {
        content: "";
        top: 0;
        bottom: 0;
        left: 0%;
        position: absolute;
        width: 100%;
        background-color: blue;
    }
}
</style>