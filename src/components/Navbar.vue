<template>
    <div>
        <nav class="bg-gray-800 p-4 shadow">
            <h1 id="companyName" class="font-bold text-2xl text-gray-200">{{ company }}</h1>
        </nav>
    </div>
</template>

<script>
export default {
    name: 'Navbar',
    props: ['company']
}
</script>

<style scoped>

</style>