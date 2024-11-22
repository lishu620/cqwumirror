<script setup lang="ts">
import { useI18n } from 'vue-i18n';
import { NH2, NP, NSpace, NButton, NButtonGroup } from 'naive-ui';

import FeedbackButton from './FeedbackButton.vue';
import NamedIcon from '@/components/NamedIcon.vue';

const { t } = useI18n();

function handleSelect(key: string) {
  window.open(key);
}
</script>

<template>
  <NH2 prefix="bar">{{ t('mirror') }}</NH2>
  <NSpace justify="space-between">
    <div>
      <NP class="footer-text">{{
        t('footer.maintainer', { name: '@m1ishu' })
      }}</NP>
      <NP class="footer-text">{{
        t('footer.developer', { name: 'm1ishu@netlab' })
      }}</NP>
      <NP class="footer-text">{{ t('footer.special') }}</NP>
    </div>
    <NButtonGroup vertical>
      <FeedbackButton />
      <NButton text @click="handleSelect('https://github.com/lishu620/cqwumirror')">
        <template #icon>
          <NamedIcon name="code" :size="16" />
        </template>
        {{ t('footer.source') }}
      </NButton>
      <NButton text @click="handleSelect('https://git.nju.edu.cn/nju-lug')">
        <template #icon>
          <NamedIcon name="male" :size="16" />
        </template>
        {{ t('footer.lug') }}
      </NButton>
    </NButtonGroup>
  </NSpace>
  <NP>重庆文理学院网络俱乐部</NP>
</template>

<style scoped lang="less">
.footer-text {
  font-size: 16px;
  margin: 4px 0;
}
</style>
