<template>
  <div v-html="marked(text)" class="markdown" />
</template>
<script>
import marked from 'marked'
marked.setOptions({
  renderer: new marked.Renderer(),
  gfm: true,
  tables: true,
  breaks: true,
  pedantic: true,
  sanitize: true,
  smartLists: true,
  smartypants: true,
})
export default {
  name: 'md',
  props: {
    cn: String,
    us: String,
  },
  data () {
    const { lang } = this.$route.params
    let text = ''
    const { cn, us } = this
    if (this.$slots.default && this.$slots.default[0] && this.$slots.default[0].text) {
      text = this.$slots.default[0].text
    } else {
      text = lang === 'cn' ? cn : us
    }
    text = text || ''
    text = text.split('\n').map(t => t.trim()).join('\n')
    return {
      marked,
      text,
    }
  },
}
</script>
