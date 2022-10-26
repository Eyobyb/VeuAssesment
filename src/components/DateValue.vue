<template>
  <p>
   {{dateTime}}
  </p>
</template>
<script>
export default {
    props:['date'],
    computed:{
        dateTime(){
            if(this.date){
                const newDate = new Date(this.date)
                return newDate.toLocaleDateString() 
            }else{
                return ""
            }
        }
    }
}
</script>

<style scoped>
</style>