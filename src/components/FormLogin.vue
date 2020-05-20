<template>
  <div>
    <form-helper>
      <div slot="form-header">
        <h2>LOGIN</h2>
      </div>

      <div slot="form-fields">
        <input
          type="text"
          v-model="username"
          placeholder="enter your name ..."
        />
        <div id="checkboxes">
          <label>rice</label>
          <input type="checkbox" value="rice" v-model="categories" />
          <label>chicken</label>
          <input type="checkbox" value="chicken" v-model="categories" />
          <label>ramen</label>
          <input type="checkbox" value="ramen" v-model="categories" />
        </div>
        <div id="selectbox">
          <select v-model="option">
            <option v-for="(op, i) in options" :key="i">{{ op }}</option>
          </select>
        </div>
      </div>

      <div slot="form-controls">
        <button @click.prevent="handleFuck">submit</button>
        <div>
          <h2>Preview Form</h2>
          <article>
            <h3>username</h3>
            {{ username }}
          </article>
          <article>
            <h3>Categories</h3>
            <ul>
              <ol v-for="(category, index) in categories" :key="index">
                {{
                  category
                }}
              </ol>
            </ul>
          </article>
          <article>
            <h3>selected option</h3>
            {{ option }}
          </article>
        </div>
      </div>
    </form-helper>
  </div>
</template>

<script>
import FormHelper from '@/components/FormHelper'
export default {
  name: 'FormLogin',
  data() {
    return {
      username: '',
      categories: [],
      option: '',
      options: ['lol', 'chaos', 'overwatch'],
    }
  },
  components: {
    FormHelper,
  },
  methods: {
    handleFuck() {
      const payload = {
        username: this.username,
        categories: this.categories,
        option: this.option,
      }
      this.$emit('fuck', payload)
    },
  },
}
</script>

<style lang="scss" scoped></style>
