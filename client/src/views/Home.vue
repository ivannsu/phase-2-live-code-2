<template>
  <div class="row">
    <div class="col-3">
      <Profile v-if="token && userId" />
      <Search v-if="token && userId"/>
      <RecentFollow v-if="token && userId" :doFollow="doFollow"/>
    </div>
    <div class="col-6">
      <StatusPost v-if="token && userId"/>
      <Status/>
    </div>
    <div class="col-3">
      <div class="card  mb-3" style="max-width: 18rem;">
        <Suggestion/>
      </div>
    </div>
  </div>
</template>

<script>
import Profile from '@/components/Profile.vue'
import Search from '@/components/Search.vue'
import RecentFollow from '@/components/RecentFollow.vue'
import StatusPost from '@/components/StatusPost.vue'
import Status from '@/components/Status.vue'
import Suggestion from '@/components/Suggestion.vue'

export default {
  name: 'home',
  components: {
    Profile, Search, RecentFollow, StatusPost, Status, Suggestion
  },
  computed: {
    token () {
      return this.$store.state.token
    },
    userId () {
      return this.$store.state.userId
    }
  }
}
</script>
