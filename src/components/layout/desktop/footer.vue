<template>
  <footer :id="FOOTER_ELEMENT_ID" class="footer">
    <div class="container">
      <a class="sitemap-btn" target="_blank" :href="VALUABLE_LINKS.SITE_MAP">sitemap.xml</a>
      <divider type="vertical" />
      <i18n>
        <template #zh>
          <router-link :to="aboutPageUrl" key="zh">木木书屋</router-link>
        </template>
      </i18n>
      <divider type="vertical" />
      <i18n>
        <template #zh>
          <span><a href="https://beian.miit.gov.cn" target="_blank">京ICP备13015487号-5</a></span>
        </template>
      </i18n>
    </div>
  </footer>
</template>

<script lang="ts">
  import { defineComponent } from 'vue'
  import { RouteName } from '/@/app/router'
  import { FOOTER_ELEMENT_ID } from '/@/constants/anchor'
  import { getPageRoute } from '/@/transforms/route'
  import { VALUABLE_LINKS } from '/@/config/app.config'

  export default defineComponent({
    name: 'DesktopFooter',
    setup() {
      return {
        FOOTER_ELEMENT_ID,
        VALUABLE_LINKS,
        aboutPageUrl: getPageRoute(RouteName.About)
      }
    }
  })
</script>

<style lang="scss" scoped>
  @import 'src/styles/init.scss';

  .footer {
    display: flex;
    align-items: center;
    height: $footer-height;
    @include common-bg-module();

    .container {
      color: $text-secondary;
      font-size: $font-size-h6;
      text-align: center;
      text-transform: uppercase;

      a {
        border-bottom: 1px solid transparent;
        &:hover {
          border-color: initial;
        }
      }

      .ipc {
        margin-right: $xs-gap;
      }
    }
  }
</style>
