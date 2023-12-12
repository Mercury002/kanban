<template>
    <div class="taskbar flex">
        <div class="taskbar__column flex flex-col" v-for="tab in tabsData">
            <div class="flex items-center taskbar__column--head mb-3">
                <span class="block rounded-full mr-2" :style="{ backgroundColor: tab.tabColor }"></span>
                <p class="font-bold taskbar__column--header">{{tab.tabName + '(' + tab.tasks.length + ')'}}</p>
            </div>

            <div class="flex flex-col items-start">
                <div class="taskbar__column--task" v-for="item in tab.tasks" @click="openTask(item)">
                    <p class="taskbar__column--title">{{ item.title }}</p>
                    <p class="taskbar__column--subtask">{{ item.doneTask + ' of ' + item.allTask + ' subtasks' }}</p>
                </div>
            </div>
        </div>

        <div class="taskbar__column flex flex-col">
            <div class="taskbar__column--create">
                <span><span>+</span> New Column</span>
            </div>
        </div>
    </div>
</template>

<script>
import data from '../data.json'

export default {
    name: "taskbarComponent",
    
    methods: {
        openTask(data) {
            console.log(data)
        }
    },

    computed: {
        tabsData() {
            return data
        }
    }
}
</script>

<style lang="scss">
.taskbar {
    padding: 20px 20px;
    width: 100%;
    overflow: auto;

    &__column {
        margin-right: 30px;

        &--head {

            & span {
                width: 20px;
                height: 20px;
            }
        }

        &--header {
            letter-spacing: 3px;
            font-size: 12px;
            color: #6a707e;
            text-transform: uppercase;
        }

        &--task {
            width: 300px;
            height: auto;
            padding: 15px 15px;
            background-color: #2c2c38;
            border-radius: 8px;
            margin-top: 10px;
            box-shadow: 1px 1px 5px #2c2c38;
            transition: .2s box-shadow;
            cursor: pointer;
        }

        &--task:hover {
            box-shadow: 0px 0px 7px #49495c;
        }

        &--task:active {
            box-shadow: 0px 0px 15px #49495c;
        }

        &--title {
            font-size: 18px;
            font-weight: 500;
            letter-spacing: 1px;
            line-height: 20px;
        }

        &--subtask {
            font-size: 14px;
            color: #898f9d;
            font-weight: 500;
            letter-spacing: 1px;
            margin-top: 5px;
        }

        &--create {
            box-shadow: 1px 1px 5px #22252e;
            background-color: #22252e;
            border-radius: 8px;
            width: 300px;
            height: 100%;
            display: flex;
            justify-content: center;
            align-items: center;
            cursor: pointer;

            & span {
                font-size: 20px;
                letter-spacing: 2px;
                color: #828d9f;
            }
        }

        &--create:hover {
            box-shadow: 0px 0px 7px #393e4d;
        }
    }

    // scrollbar-width: thin;
    // scrollbar-color: #111 #ddd;
}

// /* for other browsers */
// .taskbar::-webkit-scrollbar {
//     width: 6px;
//     background-color: transparent;
//     border-radius: 20px;
// }

// .taskbar::-webkit-scrollbar-thumb {
//     background-color: #111;
//     border-radius: 20px;
// }
</style>