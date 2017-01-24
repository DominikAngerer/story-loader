<template>
  <div class="uk-form-row">
    <select class="uk-width-1-1" v-model="model.value">
        <option></option>
        <option v-for="loadedStory in data.loadedStories" v-bind:value="loadedStory.uuid">{{ loadedStory.name }}</option>
      </select>
  </div>
</template>

<script>
  export default {
    plugin: 'story-loader',
    mixins: [window.Storyblok.plugin],
    data: {
      loadedStories: []
    },
    methods: {
      initWith: function () {
        return {
          value: ''
        }
      }
    },
    events: {
      'plugin:created': function () {
        if (!this.schema.options) {
          console.error('story-loader: Define the following options: 0 : token, 1 : starts_with');
          return false;
        }
        jQuery.ajax({
          url: 'https://api.storyblok.com/v1/cdn/stories/?token=' + this.schema.options[0].value + '&starts_with=' + this.schema.options[1].value + '/&is_startpage=false&time=' + Date.now(),
          success: (response) => {
            this.$set('data.loadedStories', response.stories);
          }
        });
      },
      'plugin:destroyed': function () {
      }
    },
    watch: {
      'model': {
        handler: function (value) {
          this.$emit('changed-model', value);
        },
        deep: true
      }
    }
  }

</script>