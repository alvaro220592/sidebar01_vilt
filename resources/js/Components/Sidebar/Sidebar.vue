<template>
    <!-- <div v-if="show" class="h-screen fixed top-0 w-full bg-black/25 backdrop-blur"></div> -->

    <aside 
        class="fixed bg-teal-600  text-white h-screen top-0 transition-all duration-500 p-3"
        :class="show ? 'sidebar_expanded' : 'sidebar_collapsed'"
    >
        <span @click="$emit('close')" class="cursor-pointer w-full">
            Fechar
        </span>

        <!-- <slot></slot> -->

            <ul class="mt-14 menu_ul">
                <li class="block">
                    <div class="flex cursor-pointer" @click="dashboard_expanded = !dashboard_expanded">
                        <font-awesome-icon icon="fa-solid fa-chart-simple" class="menu_li my-2 text-2xl" />
                        <span class="my-2 mx-4" :class="show ? '' : 'hidden'">
                            Dashboard
                        </span>
                    </div>
                    <ul class="flex flex-col px-4" :class="dashboard_expanded && show ? '' : 'hidden'">
                        <li class="flex flex-row">
                            <font-awesome-icon icon="fa-regular fa-snowflake" class="mx-2 my-1" />
                            <span>teste</span>
                        </li>

                        <li class="flex flex-row">
                            <font-awesome-icon icon="fa-regular fa-snowflake" class="mx-2 my-1" />
                            <span>teste</span>
                        </li>

                        <li class="flex flex-row">
                            <font-awesome-icon icon="fa-regular fa-snowflake" class="mx-2 my-1" />
                            <span>teste</span>
                        </li>

                    </ul>
                </li>

                <li class="block">
                    <div class="flex cursor-pointer" @click="cadastros_expanded = !cadastros_expanded">
                        <font-awesome-icon icon="fa-solid fa-square-plus" class="menu_li my-2 text-2xl" />
                        <span class="my-2 mx-4" :class="show ? '' : 'hidden'">
                            Cadastros
                        </span>
                    </div>
                    <ul class="flex flex-col px-4" :class="cadastros_expanded && show ? '' : 'hidden'">
                        <li class="flex flex-row">
                            <font-awesome-icon icon="fa-regular fa-snowflake" class="mx-2 my-1" />
                            <span>teste</span>
                        </li>

                        <li class="flex flex-row">
                            <font-awesome-icon icon="fa-regular fa-snowflake" class="mx-2 my-1" />
                            <span>teste</span>
                        </li>

                        <li class="flex flex-row">
                            <font-awesome-icon icon="fa-regular fa-snowflake" class="mx-2 my-1" />
                            <span>teste</span>
                        </li>

                    </ul>
                </li>

                <li class="block">
                    <div class="flex cursor-pointer" @click="configuracoes_expanded = !configuracoes_expanded">
                        <font-awesome-icon icon="fa-solid fa-gear" class="menu_li my-2 text-2xl" />
                        <span class="my-2 mx-4" :class="show ? '' : 'hidden'">
                            Configurações
                        </span>
                    </div>
                    <ul class="flex flex-col px-4" :class="configuracoes_expanded && show ? '' : 'hidden'">
                        <li class="flex flex-row">
                            <font-awesome-icon icon="fa-regular fa-snowflake" class="mx-2 my-1" />
                            <span>teste</span>
                        </li>

                        <li class="flex flex-row">
                            <font-awesome-icon icon="fa-regular fa-snowflake" class="mx-2 my-1" />
                            <span>teste</span>
                        </li>

                        <li class="flex flex-row">
                            <font-awesome-icon icon="fa-regular fa-snowflake" class="mx-2 my-1" />
                            <span>teste</span>
                        </li>

                    </ul>
                </li>

                <li class="block">
                    <div class="flex cursor-pointer">
                        <font-awesome-icon icon="fa-solid fa-power-off" class="menu_li my-2 text-2xl" />
                        <span class="my-2 mx-4" :class="show ? '' : 'hidden'">
                            Sair
                        </span>
                    </div>
                </li>

            </ul>
    </aside>

</template>

<script setup>
    import { ref } from 'vue';
    const dashboard_expanded = ref(false)
    const cadastros_expanded = ref(false)
    const configuracoes_expanded = ref(false)

    defineProps({
        show: Boolean
    })

    defineEmits([
        'close'
    ])

</script>

<style scoped>
    /* .navbar_sidebar_expanded {
        width: 10px;
    } */
    .sidebar_expanded{
        width: 180px;
    }

    .sidebar_collapsed{
        width: 46px;
    }

    .menu_ul {
        display: flex;
        flex-direction: column;
        justify-content: space-evenly;
    }
</style>