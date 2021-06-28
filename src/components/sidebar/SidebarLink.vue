<template>
  <router-link :to="to" class="link" :class="{ active: isActive }">
    <i class="icon" :class="icon" />
    <transition name="fade">
      <span v-if="!collapsed">
        <slot />
      </span>
    </transition>
  </router-link>
</template>

<script>
import { computed } from 'vue'
import { useRoute } from 'vue-router'
import { collapsed } from './state'
export default {
  props: {
    to: { type: String, required: true },
    icon: { type: String, required: true }
  },
  setup(props) {
    const route = useRoute()
    const isActive = computed(() => route.path === props.to)
    return { isActive, collapsed }
  }
}
</script>

<style lang='scss' scoped>
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.1s;
}
.fade-enter,
.fade-leave-to {
  opacity: 0;
}
.link {
  display: flex;
  align-items: center;
  cursor: pointer;
  position: relative;
  font-size: 2rem;
  font-weight: 400;
  user-select: none;
  margin: 1rem 0;
  padding-top: 25px;
    padding-bottom: 25px;
    padding-left: 16px;
  border-radius: 0.25rem;
  height: 1.5rem;
  text-decoration: none;
  span {
  color: #38c6e6;
  }
}
.link:hover {
  background: rgb(2,0,36);
background: linear-gradient(90deg, rgba(2,0,36,1) 0%, rgba(1,1,13,0.15028009494813555) 100%, rgba(0,212,255,1) 100%);
}
.link.active {
  background: rgb(2,0,36);
background: linear-gradient(90deg, rgba(2,0,36,1) 0%, rgba(1,1,13,0.15028009494813555) 100%, rgba(0,212,255,1) 100%);
}
.link .icon {
  flex-shrink: 0;
  width: 2.5rem;
  margin-right: 1rem;
  color:#01CBF9;
}
</style>