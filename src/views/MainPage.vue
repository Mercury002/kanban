<template>
    <div class="flex">
        <SidebarComponent></SidebarComponent>
        <div class="w-4/5">
            <NavbarComponent></NavbarComponent>
            <TaskbarComponent></TaskbarComponent>
        </div>
    </div>
</template>

<script>
import NavbarComponent from '@/components/navbarComponent.vue';
import SidebarComponent from '@/components/sidebarComponent.vue';
import TaskbarComponent from '@/components/taskbarComponent.vue'


export default {
    name: 'MainPage',
    components: { SidebarComponent, NavbarComponent, TaskbarComponent }
}
</script>