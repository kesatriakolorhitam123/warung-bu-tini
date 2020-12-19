<template>
<div>
    <Navbar/>
      <h2>Daftar Makanan</h2>
</div>
</template>

<script>
export default {
    name : 'Foods'

}
</script>

<script>
// @ is an alias to /src
import Navbar from '@/components/Navbar.vue'


export default {
  name: 'Foods',
  components: {
    Navbar
    
  }
}
</script>