# เปลี่ยนข้อความในฟอร์เป็นภาษาไทย
<template>
  <div class="q-pa-md" style="max-width: 400px">
<<<<<<< HEAD
=======

>>>>>>> thai-lang
    <q-form
      @submit="onSubmit"
      @reset="onReset"
      class="q-gutter-md"
    >
      <q-input
        filled
        v-model="name"
<<<<<<< HEAD
        label="Your name *"
        hint="Name and surname"
        lazy-rules
        :rules="[ val => val && val.length > 0 || 'Please type something']"
      />
=======
        label="ชื่อ-สกุล *"
        hint="ชื่อและนามสกุล"
        lazy-rules
        :rules="[ val => val && val.length > 0 || 'กรุณาพิมพ์ชื่อ']"
      />

>>>>>>> thai-lang
      <q-input
        filled
        type="number"
        v-model="age"
<<<<<<< HEAD
        label="Your age *"
        lazy-rules
        :rules="[
          val => val !== null && val !== '' || 'Please type your age',
          val => val > 0 && val < 100 || 'Please type a real age'
        ]"
      />
      <q-toggle v-model="accept" label="I accept the license and terms" />
      <div>
        <q-btn label="Submit" type="submit" color="primary"/>
        <q-btn label="Reset" type="reset" color="primary" flat class="q-ml-sm" />
=======
        label="อายุ *"
        lazy-rules
        :rules="[
          val => val !== null && val !== '' || 'กรุณาใส่อายุ',
          val => val > 0 && val < 100 || 'กรุณาใส่อายุจริง'
        ]"
      />

      <q-toggle v-model="accept" label="ยอมรับ" />

      <div>
        <q-btn label="ยอมรับ" type="submit" color="primary"/>
        <q-btn label="ยกเลิก" type="reset" color="primary" flat class="q-ml-sm" />
>>>>>>> thai-lang
      </div>
    </q-form>
  </div>
<<<<<<< HEAD
</template>
=======
</template>

<script>
import { useQuasar } from 'quasar'
import { ref } from 'vue'

export default {
  setup () {
    const $q = useQuasar()

    const name = ref(null)
    const age = ref(null)
    const accept = ref(false)
    return {
      name,
      age,
      accept,
      onSubmit () {
        if (accept.value !== true) {
          $q.notify({
            color: 'red-5',
            textColor: 'white',
            icon: 'warning',
            message: 'คุณจำเป็นต้องยอมรับ'
          })
        }
        else {
          $q.notify({
            color: 'green-4',
            textColor: 'white',
            icon: 'cloud_done',
            message: 'ข้อมูลได้รับการยืนยัน'
          })
        }
      },
      onReset () {
        name.value = null
        age.value = null
        accept.value = false
      }
    }
  }
}
</script>
>>>>>>> thai-lang
