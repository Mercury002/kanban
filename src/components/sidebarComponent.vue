<template>
    <div class="sidebar">
        <h1 class="sidebar__title">Kanban</h1>

        <div class="sidebar__boards">
            <span class="sidebar__boards--head">All boards({{ boardsList.length }})</span>

            <div class="sidebar__board" v-for="text in boardsList">
                <div class="sidebar__board-text flex items-center">
                    <AppstoreOutlined style="font-size: 20px; margin: 2px 10px 2px 0px; padding: 10px 0;" />
                    <span class="text-xl">{{ text }}</span>
                </div>
                <span class="sidebar__board-background"></span>
            </div>


            <div class="sidebar__board">
                <div class="sidebar__board-text flex items-center">
                    <AppstoreAddOutlined style="font-size: 20px; margin: 2px 10px 2px 0px; padding: 10px 0;" />
                    <span class="text-xl">Create new board</span>
                </div>
                <span class="sidebar__board-background"></span>
            </div>
        </div>
    </div>
</template>

<script>
import { AppstoreOutlined, AppstoreAddOutlined } from '@ant-design/icons-vue';

export default {
    name: 'sidebarComponent',

    components: {
        AppstoreOutlined,
        AppstoreAddOutlined
    },

    data() {
        return {
            boardsList: ['Platform launch', 'Marketing plan', 'Roadmap']
        }
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
        cursor: pointer;
        position: relative;
    }

    &__board-text {
        position: relative;
        z-index: 2;
        width: 80%;
        padding: 7px 0;
    }

    &__board-background {
        background-color: #6e7482;
        width: 95%;
        height: 85%;
        position: absolute;
        z-index: 1;
        left: -10%;
        top: 50%;
        transform: translateY(-50%);
        border-radius: 0 50px 50px 0;
        opacity: 0;
        transition: .2s opacity;
    }
}

.sidebar__board:hover .sidebar__board-background {
    opacity: 1;
}
</style>