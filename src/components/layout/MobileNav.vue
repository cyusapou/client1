<template>
  <nav class="mobile-nav">
    <div class="mobile-nav__container">
      <router-link to="/dashboard" class="nav-item" active-class="nav-item--active">
        <Icon icon="ph:squares-four" />
        <span>{{ $t('nav.dashboard') }}</span>
      </router-link>

      <router-link to="/pay" class="nav-item" active-class="nav-item--active">
        <Icon icon="ph:credit-card" />
        <span>{{ $t('nav.payments') }}</span>
      </router-link>

      <router-link to="/history" class="nav-item" active-class="nav-item--active">
        <Icon icon="ph:clock-counter-clockwise" />
        <span>{{ $t('nav.history') }}</span>
      </router-link>

      <router-link to="/account" class="nav-item" active-class="nav-item--active">
        <Icon icon="ph:user" />
        <span>{{ $t('nav.account') }}</span>
      </router-link>
    </div>
  </nav>
</template>

<script setup lang="ts">
import { Icon } from '@iconify/vue'
</script>

<style scoped>
.mobile-nav {
  position: fixed;
  bottom: 0;
  left: 0;
  right: 0;
  height: calc(var(--mobile-nav-height) + var(--safe-area-bottom));
  background: var(--glass-bg);
  backdrop-filter: blur(var(--glass-blur));
  -webkit-backdrop-filter: blur(var(--glass-blur));
  border-top: 1px solid var(--glass-border);
  box-shadow: 0 -4px 20px rgba(0, 0, 0, 0.05);
  z-index: var(--z-sticky);
  display: flex;
  align-items: flex-start;
  padding-bottom: var(--safe-area-bottom);
}

.mobile-nav__container {
  display: flex;
  justify-content: space-around;
  align-items: center;
  width: 100%;
  height: var(--mobile-nav-height);
}

.nav-item {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 4px;
  color: var(--color-neutral-400);
  text-decoration: none;
  font-size: 10px;
  font-weight: 600;
  padding: 8px;
  transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
  min-width: 64px;
}

.nav-item svg {
  width: 24px;
  height: 24px;
  transition: transform 0.3s var(--ease-bounce);
}

.nav-item--active {
  color: var(--color-primary-600);
}

.nav-item--active svg {
  transform: translateY(-2px) scale(1.1);
  color: var(--color-primary-600);
}

.nav-item span {
  opacity: 0.8;
}

.nav-item--active span {
  opacity: 1;
}

@media (min-width: 769px) {
  .mobile-nav {
    display: none;
  }
}
</style>
