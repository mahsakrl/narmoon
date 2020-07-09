<template>
  <q-card class="my-card shadow-2 shadow-up-1" bordered>
    <div class="row fit">
      <div class="flex-center flex col-3 q-pa-xs">
        <q-img width="80px" class="rounded-img" src="https://cdn.quasar.dev/img/parallax2.jpg" />
      </div>
      <div class="col-9 row q-pa-xs">
        <div>
          <div class="text-overline text-accent">{{cardData.category.label}}</div>
          <div class="text-caption text-weight-bold q-mb-xs">{{cardData.title}}</div>
        </div>
        <div class="text-caption text-grey flex row col-12">
          <q-btn size="xs" icon="alarm" label flat unelevated>
            <span class="q-px-xs">{{cardData.uploadedTime | toPersianNumber}} ساعت پیش</span>
          </q-btn>
          <q-btn size="xs" icon="mdi-comment-processing-outline" label flat unelevated>
            <span class="q-px-xs">{{cardData.comment | toPersianNumber}} دیدگاه</span>
          </q-btn>
          <q-btn size="xs" icon="mdi-book-open-outline" label flat unelevated>
            <span class="q-px-xs">{{cardData.readTime.value | toPersianNumber}}</span>
            <span>{{cardData.readTime.unit | toPersianUnit}}</span>
          </q-btn>
        </div>
      </div>
    </div>
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
.my-card {
  border-radius: 10px;
}
.rounded-img {
  border-radius: 10px;
}
</style>
 