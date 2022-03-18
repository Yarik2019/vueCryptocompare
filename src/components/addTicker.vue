<template>
  <section>
    <div class="flex">
      <div class="max-w-xs">
        <label for="wallet" class="block text-sm font-medium text-gray-700"
          >Тикер</label
        >
        <div class="mt-1 relative rounded-md shadow-md">
          <input
            type="text"
            name="wallet"
            v-model="ticker"
            @keydown.enter="add"
            id="wallet"
            class="
              block
              w-full
              pr-10
              border-gray-300
              text-gray-900
              focus:outline-none focus:ring-gray-500 focus:border-gray-500
              sm:text-sm
              rounded-md
            "
            placeholder="Например DOGE"
          />
        </div>
      </div>
    </div>
    <add-button  @click="add"/>
  </section>
</template>
<script>
import addButton from "../components/addButton.vue";
export default {
  props:{
      disabled: {
          type: Boolean,
          required: false,
          default: false
      }
  },  
  data() {
    return {
        ticker: ''
    };
  },
  components: {
    addButton,
  },
  methods:{
    add() {
      this.$emit('add-ticker', this.ticker);
      this.ticker = "";
    },
  }
};
</script>
