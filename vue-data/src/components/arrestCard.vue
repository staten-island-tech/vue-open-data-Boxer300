 <template>
  <div  class="card">
   {{ arrest }}
  </div>
</template>

<script setup>


const props = defineProps({
  arrest: { type: Object},

})

</script> 