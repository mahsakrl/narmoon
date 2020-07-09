<template>
  <q-card flat>
    <q-card-section class>
      <q-card-section class="flex-center flex">
        <q-img class="rounded-img fit-width" src="https://cdn.quasar.dev/img/parallax2.jpg" />
      </q-card-section>
      <q-card-section>
        <div class="text-overline text-accent">{{cardData.category.label}}</div>
        <div class="text-subtitle2 q-mb-xs">{{cardData.title}}</div>
        <div class="text-caption text-grey flex row">
          <q-btn size="xs" icon="alarm" label flat unelevated>
            <span class="q-px-xs">ُ{{cardData.uploadedTime | toPersianNumber}} ساعت پیش</span>
          </q-btn>
          <q-btn size="xs" icon="mdi-comment-processing-outline" label flat unelevated>
            <span class="q-px-xs">{{cardData.comment | toPersianNumber}}دیدگاه</span>
          </q-btn>
          <q-btn size="xs" icon="mdi-book-open-outline" label flat unelevated>
            <span class="q-px-xs">{{cardData.readTime.value | toPersianNumber}}</span>
            <span>{{cardData.readTime.unit | toPersianUnit}}</span>
          </q-btn>
        </div>
      </q-card-section>
    </q-card-section>
  </q-card>
</template>
<script>
import persianJs from 'persianjs'
export default {
  data() {
    return {
      cardData: {
        title: 'چگونه شروع به یادگیری سینما فوردی کنیم ',
        category: { label: 'دیزاین', value: 'design' },
        image: '../assets/quasar-logo-full.svg',
        readTime: { unit: 'min', value: '4' },
        uploadedTime: '6',
        comment: '34'
      }
    }
  },
  filters: {
    toPersianNumber: function(value) {
      return persianJs(value).englishNumber()
    },
    toPersianUnit: function(value) {
      switch (value) {
        case 'min':
          return 'دقیقه'
          break
        case 'hour':
          return 'ساعت'
          break

        default:
          break
      }
    }
  }
}
</script>
<style lang="scss" scoped>
.rounded-img {
  border-radius: 15px;
}
</style>
 