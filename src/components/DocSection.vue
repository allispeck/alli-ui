<template>
    <div class="doc-section">
        <h3>{{title}}</h3>
        <div class="components">
            <slot></slot>
        </div>
    </div>
</template>

<script>
  export default {
    props:{
      title:{
        type:String,
        default: "Insert Title",
        required: false
      }
    }
  };
</script>

<style lang="scss" scoped>
    .doc-section {
        box-shadow:  -20px 20px 60px #d9d9d9,
        20px -20px 60px #ffffff;
        margin : 3rem;
        padding: 1rem;
        border-radius: 0.5rem;

        h3 {
            margin-top: 0.5rem;
        }
        .components {
            display         : flex;
            justify-content : center;
        }
    }
</style>