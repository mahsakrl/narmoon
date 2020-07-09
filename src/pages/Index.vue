<template>
  <q-page class="flex flex-center">
    <q-card>
      <q-card-section>
        <q-card flat>
          <q-item>
            <q-item-section avatar>
              <q-avatar square>
                <img src="https://cdn.quasar.dev/img/avatar3.jpg" />
              </q-avatar>
            </q-item-section>
          </q-item>
          <q-item>
            <q-item-section>
              <q-item-label class="text-h6">درباره دیزاین، هنر و همه چیز</q-item-label>
              <q-item-label caption>ویلاگ شخصی نرگس غریب</q-item-label>
            </q-item-section>
          </q-item>
        </q-card>
      </q-card-section>
      <q-card-section>
        <Search />
      </q-card-section>
      <q-card-section>
        <q-tabs
          v-model="tab"
          dense
          class="text-grey row"
          active-color="accent"
          indicator-color="accent"
        >
          <q-tab name="all" label="همه" content-class="col-12" />
          <q-tab name="design" label="دیزاین" content-class="col-12" />
          <q-tab name="art" label="هنر" content-class="col-12" />
          <q-tab name="tech" label="تکنولوژی" content-class="col-12" />
          <q-tab name="ui" label="UI/UX" content-class="col-12" />
        </q-tabs>

        <q-tab-panels v-model="tab" animated>
          <q-tab-panel name="all">
            <BlogCardView />
            <q-card flat class="flex-end flex">
              <q-tabs
                v-model="tabPop"
                dense
                class="text-grey"
                active-color="accent"
                indicator-color="accent"
                align="justify"
                narrow-indicator
              >
                <q-tab name="pop" label="محوب ترین ها" />
              </q-tabs>

              <q-tab-panels v-model="tabPop" animated>
                <q-tab-panel name="pop">
                  <BlogCard />
                </q-tab-panel>
              </q-tab-panels>
            </q-card>
          </q-tab-panel>
        </q-tab-panels>
      </q-card-section>
    </q-card>
  </q-page>
</template>

<script>
import BlogCard from '../components/BlogCard'
import BlogCardView from '../components/BlogCardView'
import Search from '../components/Search'
export default {
  name: 'PageIndex',
  data() {
    return {
      tab: 'all',
      tabPop: 'pop'
    }
  },
  components: {
    BlogCard,
    BlogCardView,
    Search
  }
}
</script>
