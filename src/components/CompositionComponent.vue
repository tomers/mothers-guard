<template>
  <q-list >
    <q-item clickable v-for="todo in todos" :key="todo.id" tag="a" target="_blank" :href="todo.url">
      <q-item-label>
        {{ todo.content }}
      </q-item-label>
    </q-item>
  </q-list>
</template>

<script lang="ts">
import {
  defineComponent, PropType, computed, /* ref, */ toRef, Ref
} from '@vue/composition-api'
import { Todo, Meta } from './models'

// function useClickCount () {
//   const clickCount = ref(0)
//   function increment () {
//     clickCount.value += 1
//     return clickCount.value
//   }

//   return { clickCount, increment }
// }

function useDisplayTodo (todos: Ref<Todo[]>) {
  const todoCount = computed(() => todos.value.length)
  return { todoCount }
}

export default defineComponent({
  name: 'CompositionComponent',
  props: {
    title: {
      type: String,
      required: true
    },
    todos: {
      type: (Array as unknown) as PropType<Todo[]>,
      default: () => []
    },
    meta: {
      type: (Object as unknown) as PropType<Meta>,
      required: true
    },
    active: {
      type: Boolean
    }
  },
  setup (props) {
    return { /* ...useClickCount(), */ ...useDisplayTodo(toRef(props, 'todos')) }
  }
})
</script>
