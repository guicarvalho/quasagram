<template>
  <q-page class="constrain q-pa-md">

    <div class="row q-col-gutter-lg">
      <div class="col-12 col-sm-8">
        <q-card
          v-for="post in posts"
          :key="post.id"
          class="card-post q-mb-md"
          flat
          bordered
        >
          <q-item>
            <q-item-section avatar>
              <q-avatar>
                <img src="https://s.gravatar.com/avatar/553c93e4fea69896da48deda408c8903?s=80">
              </q-avatar>
            </q-item-section>

            <q-item-section>
              <q-item-label class="text-bold">decarvalho.gui</q-item-label>
              <q-item-label
                caption
              >
                {{ post.location }}
              </q-item-label>
            </q-item-section>
          </q-item>

          <q-separator />

          <q-img
            :src="post.imageUrl"
          />

          <q-card-section>
            <div>{{ post.caption }}</div>
            <div
              class="text-caption text-grey"
            >
              {{ post.date | formatDate }}
            </div>
          </q-card-section>
        </q-card>
      </div>

      <div class="col-4 large-screen-only">
        <q-item class="fixed">
          <q-item-section avatar>
            <q-avatar size="50px">
              <img src="https://s.gravatar.com/avatar/553c93e4fea69896da48deda408c8903?s=80">
            </q-avatar>
          </q-item-section>

          <q-item-section>
            <q-item-label class="text-bold">decarvalho.gui</q-item-label>
            <q-item-label caption>Guilherme de Carvalho</q-item-label>
          </q-item-section>
        </q-item>
      </div>
    </div>

  </q-page>
</template>

<script>
import { date } from "quasar";

export default {
  name: 'PageHome',
  data() {
    return {
      posts: [
        {
          id: 1,
          caption: "Hora do almoço",
          date: 1599942014078,
          location: "Araraquara, São Paulo",
          imageUrl: "https://cdn.quasar.dev/img/chicken-salad.jpg"
        },
        {
          id: 2,
          caption: "Hora do almoço",
          date: Date.now(),
          location: "Araraquara, São Paulo",
          imageUrl: "https://cdn.quasar.dev/img/parallax2.jpg"
        },
        {
          id: 3,
          caption: "Hora do almoço",
          date: Date.now(),
          location: "Araraquara, São Paulo",
          imageUrl: "https://cdn.quasar.dev/img/mountains.jpg"
        },
        {
          id: 4,
          caption: "Hora do almoço",
          date: Date.now(),
          location: "Araraquara, São Paulo",
          imageUrl: "https://cdn.quasar.dev/img/parallax1.jpg"
        }
      ]
    }
  },
  filters: {
    formatDate(value) {
      return date.formatDate(value, "D MMMM h:mm")
    }
  }
}
</script>

<style lang="sass">
  .card-post
    .q-img
      min-height: 200px
</style>
