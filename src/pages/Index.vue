<template>
  <q-page class="row items-center justify-evenly">
    <example-component
      title="Example component"
      active
      :todos="todos"
      :meta="meta"
    ></example-component>
  </q-page>
</template>

<script lang="ts">
import { Todo, Meta } from 'components/models'
import ExampleComponent from 'components/CompositionComponent.vue'
import { defineComponent, ref } from '@vue/composition-api'

export default defineComponent({
  name: 'PageIndex',
  components: { ExampleComponent },
  setup () {
    const todos = ref<Todo[]>([
      {
        id: 1,
        content: 'חיי הפכו לסיוט: החלק בשני בחשיפת רשת הפדופילים ב-עושים צהריים עם יעל דן',
        url: 'https://glz.co.il/%D7%92%D7%9C%D7%A6/%D7%AA%D7%95%D7%9B%D7%A0%D7%99%D7%95%D7%AA/%D7%A2%D7%95%D7%A9%D7%99%D7%9D-%D7%A6%D7%94%D7%A8%D7%99%D7%99%D7%9D/%D7%A2%D7%95%D7%A9%D7%99%D7%9D-%D7%A6%D7%94%D7%A8%D7%99%D7%99%D7%9D01-03-2021-1301/%D7%97%D7%99%D7%99-%D7%94%D7%A4%D7%9B%D7%95-%D7%9C%D7%A1%D7%99%D7%95%D7%98-%D7%94%D7%97%D7%9C%D7%A7-%D7%91%D7%A9%D7%A0%D7%99-%D7%91%D7%97%D7%A9%D7%99%D7%A4%D7%AA-%D7%A8%D7%A9%D7%AA-%D7%94%D7%A4%D7%93%D7%95%D7%A4%D7%99%D7%9C%D7%99%D7%9D-%D7%91-%D7%A2%D7%95%D7%A9%D7%99%D7%9D-%D7%A6%D7%94%D7%A8%D7%99%D7%99%D7%9D'
      },
      {
        id: 2,
        content: 'כל הורה חייב לראות את תחקיר המקור על הפגיעות המיניות בשכונה חרדית בירושלים',
        url: 'https://www.haaretz.co.il/gallery/television/tv-review/.premium.HIGHLIGHT-1.8228202'
      },
      {
        id: 3,
        content: 'לא מחכות לעירייה: סיירת נשים תוקם בחיפה בעקבות תחקיר עושים צהריים עם יעל דן',
        url: "https://glz.co.il/%D7%92%D7%9C%D7%A6/%D7%AA%D7%95%D7%9B%D7%A0%D7%99%D7%95%D7%AA/%D7%A2%D7%95%D7%A9%D7%99%D7%9D-%D7%A6%D7%94%D7%A8%D7%99%D7%99%D7%9D/%D7%A2%D7%95%D7%A9%D7%99%D7%9D-%D7%A6%D7%94%D7%A8%D7%99%D7%99%D7%9D02-03-2021-1301/%D7%9C%D7%90-%D7%9E%D7%97%D7%9B%D7%95%D7%AA-%D7%9C%D7%A2%D7%99%D7%A8%D7%99%D7%99%D7%94-%D7%A1%D7%99%D7%99%D7%A8%D7%AA-%D7%A0%D7%A9%D7%99%D7%9D-%D7%AA%D7%95%D7%A7%D7%9D-%D7%91%D7%97%D7%99%D7%A4%D7%94-%D7%91%D7%A2%D7%A7%D7%91%D7%95%D7%AA-%D7%AA%D7%97%D7%A7%D7%99%D7%A8-%D7%A2%D7%95%D7%A9%D7%99%D7%9D-%D7%A6%D7%94%D7%A8%D7%99%D7%99%D7%9D"
      }
    ])
    const meta = ref<Meta>({
      totalCount: 1200
    })
    return { todos, meta }
  }
})
</script>
