<template>
  <div class="home">
    <img
      alt="home-logo"
      src="@/assets/small-groot.png"
      style="max-height:200px;"
    />

    <h1>Welcome to Groot-Ipsum</h1>

    <textarea v-model="textContent" name="groot-ipsum" id="copy-area" readonly>
      I am groot.
    </textarea>

    <div class="generate">
      <form>
        <input v-model="paragraphs" type="number" class="generate-input" />
        <input
          type="submit"
          value="Generate"
          class="btn generate-button"
          @click.prevent="generate(paragraphs)"
        />
      </form>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Home',
  data() {
    return {
      textContent: '',
      paragraphs: 3
    }
  },
  created() {
    this.textContent = `I am groot I am groot I am groot I am groot. I am groot I am groot I am groot I am groot. I am groot I am groot I am groot I am groot I am groot. \n\nI am groot I am groot I am groot I am groot. I am groot I am groot I am groot I am groot. I am groot I am groot I am groot I am groot I am groot. I am groot I am groot I am groot I am groot I am groot. \n\nI am groot I am groot I am groot I am groot. I am groot I am groot I am groot I am groot.`
  },
  methods: {
    sentence() {
      const times = Math.ceil(Math.random() * 10)
      let text = ''
      for (let i = 0; i < times; i++) {
        text = text + 'I am groot'
        if (i < times - 1) {
          text = text + ' '
        } else {
          text = text + '.'
        }
      }
      return text
    },
    paragraph() {
      const times = Math.ceil(Math.random() * 5)
      let text = ''
      for (let i = 0; i < times; i++) {
        text = text + this.sentence()
        if (i < times - 1) {
          text = text + ' '
        }
      }
      return text
    },
    generate(paragraphs) {
      let generatedText = ''
      for (let i = 0; i < paragraphs; i++) {
        generatedText += this.paragraph() + ` \n\n`
      }
      this.textContent = generatedText
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
*:not(h1) {
  color: #3070b1;
  font-size: 16px;
  font-family: 'Underdog', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
#copy-area {
  width: 100%;
  height: 250px;
  background: #222;
  border: 1px solid #151515;
  resize: none;
  transition: box-shadow 0.2s ease;
  &:focus {
    outline: none;
    box-shadow: #3070b1 0 0 3px 2px;
  }
}
.generate {
  margin: 10px auto;
  width: 100%;
  display: flex;
  justify-content: center;

  &-input {
    width: 35px;
    height: 25px;
    background: #222;
    border: 1px solid #151515;
    font-weight: bold;
    margin-right: 20px;
    padding-left: 10px;
    transition: box-shadow 0.2s ease;
    &:hover {
      box-shadow: #3070b1 0 0 3px 1px;
    }
    &:focus {
      outline: none;
      box-shadow: #3070b1 0 0 3px 1px;
    }
  }
  &-button {
    padding: 5px 15px;
    background: #3070b1;
    border: 1px solid #151515;
    color: #222;
    font-weight: bold;
    transition: all 0.2s ease;
    cursor: pointer;
    &:hover {
      background: #2060a0;
      color: #151515;
    }
    &:focus {
      outline: none;
      box-shadow: #3070b1 0 0 3px 1px;
    }
  }
}

</style>
