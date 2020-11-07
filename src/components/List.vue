<template>
    <div>
        <h4>{{ title }}</h4>
        <div class="table">
            <thead>
                <tr>
                    <th>Name</th>
                    <th>Email</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="item in items" :key="item.id" @click="handleClick(item)">
                    <td>
                        {{ item.name }}
                    </td>
                    <td>
                        {{ item.email }}
                    </td>
                </tr>
            </tbody>
        </div>
    </div>
</template>

<script>

export default {
    props: ['items', 'title', 'handleClick'],
}
</script>

<style>

</style>