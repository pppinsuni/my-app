<script lang="ts">
  export let text : string;
  export let onClick : ()=>void;
  // 함수 타입 
  export let color : 'orange' | 'grey'| 'dark-grey';
</script>

<div class="button" data-color={color} 
onclick={()=> onClick(text)}>{text}</div>

<style lang="scss">
  .button {
    width: 80px;
    height: 80px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 24px;
    font-weight: 600;
    &[data-color='orange'] {
      background-color:orange;
      // 계층적 표현이 가능
    }
    &[data-color='darkgrey'] {
      background-color:darkgrey;
      // 계층적 표현이 가능
    }
    &[data-color='grey'] {
      background-color:grey;
      // 계층적 표현이 가능
    }
  }
</style>