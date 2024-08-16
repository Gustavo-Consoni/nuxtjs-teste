<script setup>
    const products = await useFetch('https://fakestoreapi.com/products').data
</script>

<template>
    <section class="text-gray-600">
        <div class="px-5 py-24 mx-auto container">
            <div class="flex flex-wrap -m-4">
                <div class="w-full md:w-1/2 lg:w-1/4 p-4" v-for="product in products">
                    <a class="block relative h-64 rounded overflow-hidden">
                        <img alt="ecommerce" class="block w-full h-full object-center object-cover" :src="product.image">
                    </a>
                    <div class="mt-4">
                        <h3 class="text-xs text-gray-500 tracking-widest mb-1">{{ product.category }}</h3>
                        <h2 class="text-lg text-gray-900 font-medium">{{ product.title }}</h2>
                        <p class="mt-1">R$ {{ product.price }}</p>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>
