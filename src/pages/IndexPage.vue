<template>
  <div class="q-pa-md" style="max-width: 400px">

    <q-form @submit="onSubmit" @reset="onReset" class="q-gutter-md">
      <q-input filled v-model="name" label="ชื่อ-นามสกุล *" hint="กรุณากรอกชื่อ-นามสกุล" lazy-rules
        :rules="[val => val && val.length > 0 || 'กรุณากรอกชื่อ-นามสกุลให้ถูกต้อง']" />

      <q-input filled type="number" v-model="age" label="อายุ 123454*" lazy-rules :rules="[
        val => val !== null && val !== '' || 'กรุณากรอกอายุจริงๆ',
        val => val > 0 && val < 100 || 'กรุณากรอกอายุให้ถูกต้อง (1-99abc)'
      ]" />

      <q-toggle v-model="accept" label="I accept the license and terms" />

      <div>
        <q-btn label="Submit" type="submit" color="primary" />
        <q-btn label="Reset" type="reset" color="primary" flat class="q-ml-sm" />
      </div>
    </q-form>

  </div>
</template>

<script>
import { useQuasar } from 'quasar'
import { ref } from 'vue'

export default {
  setup() {
    const $q = useQuasar()

    const name = ref(null)
    const age = ref(null)
    const accept = ref(false)

    return {
      name,
      age,
      accept,

      onSubmit() {
        if (accept.value !== true) {
          $q.notify({
            color: 'red-5',
            textColor: 'white',
            icon: 'warning',
            message: 'You need to accept the license and terms first'
          })
        }
        else {
          $q.notify({
            color: 'green-4',
            textColor: 'white',
            icon: 'cloud_done',
            message: 'Submitted'
          })
        }
      },

      onReset() {
        name.value = null
        age.value = null
        accept.value = false
      }
    }
  }
}
</script>