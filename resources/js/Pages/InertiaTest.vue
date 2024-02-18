<script setup> 
    import {Link} from '@inertiajs/vue3'; 
    import { ref } from 'vue';

    const newTitle = ref('');
    const newContent = ref('');
</script>

<template>
    <div>
        <h1>Inertia Test</h1>
        <a href="/">タグ経由です</a><br>
        <a href="/">Link経由です</a><br>
        <Link :href="route('inertia.index')">名前付きルートの確認です</Link><br>
        <Link :href="route('inertia.show', { id : 1 })">パラメータ付きの名前付きルートの確認です</Link><br>
    </div>

    <div class="mb-8">
        <input type="text" name="newTitle" v-model="newTitle">{{ newTitle }}<br>
        <input type="text" name="newContent" v-model="newContent"><br>
        <Link as="button" :href="route('inertia.store')" method="post" 
        :data="{
             title: newTitle, content: newContent
            }">新規作成</Link>

    </div>  
</template>