<template>
    <div class="taskbar flex">
        <div class="taskbar__column flex flex-col">
            <div class="flex items-center taskbar__column--head mb-3">
                <span class="block rounded-full bg-white mr-2"></span>
                <p class="font-bold taskbar__column--header">TODO(4)</p>
            </div>

            <div class="flex flex-col items-start">
                <div class="taskbar__column--task">
                    <p class="taskbar__column--title">Build UI for onboarding flow</p>
                    <p class="taskbar__column--subtask">0 of 3 subtasks</p>
                </div>
                <div class="taskbar__column--task">
                    <p class="taskbar__column--title">Build UI for search</p>
                    <p class="taskbar__column--subtask">0 of 1 subtasks</p>
                </div>
                <div class="taskbar__column--task">
                    <p class="taskbar__column--title">Build settings UI</p>
                    <p class="taskbar__column--subtask">0 of 2 subtasks</p>
                </div>
                <div class="taskbar__column--task">
                    <p class="taskbar__column--title">QA and test all major user journeys</p>
                    <p class="taskbar__column--subtask">0 of 2 subtasks</p>
                </div>
            </div>
        </div>

        <div class="taskbar__column flex flex-col">
            <div class="flex items-center taskbar__column--head mb-3">
                <span class="block rounded-full bg-sky-700 mr-2"></span>
                <p class="font-bold taskbar__column--header">DOING(6)</p>
            </div>

            <div class="flex flex-col items-start">
                <div class="taskbar__column--task">
                    <p class="taskbar__column--title">Design settings and search pages</p>
                    <p class="taskbar__column--subtask">1 of 3 subtasks</p>
                </div>
                <div class="taskbar__column--task">
                    <p class="taskbar__column--title">Add account management endpoints</p>
                    <p class="taskbar__column--subtask">2 of 3 subtasks</p>
                </div>
                <div class="taskbar__column--task">
                    <p class="taskbar__column--title">Design onboarding flow</p>
                    <p class="taskbar__column--subtask">1 of 3 subtasks</p>
                </div>
                <div class="taskbar__column--task">
                    <p class="taskbar__column--title">Add search endpoints</p>
                    <p class="taskbar__column--subtask">1 of 2 subtasks</p>
                </div>
                <div class="taskbar__column--task">
                    <p class="taskbar__column--title">Add authentication endpoints</p>
                    <p class="taskbar__column--subtask">1 of 2 subtasks</p>
                </div>
                <div class="taskbar__column--task">
                    <p class="taskbar__column--title">Research pricing points of various competitors and trial different
                        business models</p>
                    <p class="taskbar__column--subtask">2 of 3 subtasks</p>
                </div>
            </div>
        </div>

        <div class="taskbar__column flex flex-col">
            <div class="flex items-center taskbar__column--head mb-3">
                <span class="block rounded-full bg-yellow-600 mr-2"></span>
                <p class="font-bold taskbar__column--header">Done(6)</p>
            </div>

            <div class="flex flex-col items-start">
                <div class="taskbar__column--task">
                    <p class="taskbar__column--title">Conduct 5 wireframes tests</p>
                    <p class="taskbar__column--subtask">1 of 1 subtasks</p>
                </div>
                <div class="taskbar__column--task">
                    <p class="taskbar__column--title">Create wireframe prototype</p>
                    <p class="taskbar__column--subtask">1 of 1 subtasks</p>
                </div>
                <div class="taskbar__column--task">
                    <p class="taskbar__column--title">Review results of usability tests and iterate</p>
                    <p class="taskbar__column--subtask">3 of 3 subtasks</p>
                </div>
                <div class="taskbar__column--task">
                    <p class="taskbar__column--title">Create paper prototypes and conduct 10 usability tests with potencial
                        customers</p>
                    <p class="taskbar__column--subtask">2 of 2 subtasks</p>
                </div>
                <div class="taskbar__column--task">
                    <p class="taskbar__column--title">Market discovery</p>
                    <p class="taskbar__column--subtask">1 of 1 subtasks</p>
                </div>
                <div class="taskbar__column--task">
                    <p class="taskbar__column--title">Compititor analysis</p>
                    <p class="taskbar__column--subtask">3 of 3 subtasks</p>
                </div>
                <div class="taskbar__column--task">
                    <p class="taskbar__column--title">Create paper prototypes and conduct 10 usability tests with potencial
                        customers</p>
                    <p class="taskbar__column--subtask">2 of 2 subtasks</p>
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
export default {
    name: "taskbarComponent"
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