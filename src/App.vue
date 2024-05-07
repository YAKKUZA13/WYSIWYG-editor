<template>
  <div>
    <editor-content :editor="editor" class="edit" />
    <button @click="saveContent">Сохранить</button>
  </div>
</template>

<script setup>
import { useEditor, EditorContent } from '@tiptap/vue-3'
import StarterKit from '@tiptap/starter-kit'

const editor = useEditor({
  extensions: [StarterKit],
  content: `<p>Привет, это тестовый текст</p><div> Новый текст</div>`, // Прередать HTML контент
})

// Функция для сохранения содержимого редактора
const saveContent = () => {
  if (editor.value) {
    const html = editor.value.getHTML();
    console.log(html); // Для демонстрации
  }
}
</script>

<style scoped>
.edit{
  width: 500px;
}
</style>