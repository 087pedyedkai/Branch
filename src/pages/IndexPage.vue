# เปลี่ยนข้อความในฟอร์เป็นภาษาไทย
# เปลี่ยนข้อความในฟอร์เป็นภาษาไทย
<template>
  <div class="q-pa-md" style="max-width: 400px">


    <q-form
      @submit="onSubmit"
      @reset="onReset"
      class="q-gutter-md"
    >
      <q-input
        filled
        v-model="name"
        label="ชื่อ-สกุล *"
        hint="ชื่อและนามสกุล"
        label="ชื่อ-สกุล *"
        hint="ชื่อและนามสกุล"
        lazy-rules
        :rules="[ val => val && val.length > 0 || 'กรุณาพิมพ์ชื่อ']"
        :rules="[ val => val && val.length > 0 || 'กรุณาพิมพ์ชื่อ COLD']"
      />


      <q-input
        filled
        type="number"
        v-model="age"
        label="อายุ *"
        label="อายุ *"
        lazy-rules
        :rules="[
<<<<<<< HEAD
<<<<<<< HEAD
          val => val !== null && val !== '' || 'กรุณาพิมพ์อายุของคุณนะครับ',
          val => val > 0 && val < 100 || 'กรุณาพิมพ์อายุที่ถูกต้องนะจ๊ะ '
=======
          val => val !== null && val !== '' || 'กรุณาใส่อายุ',
          val => val > 0 && val < 100 || 'กรุณาใส่อายุจริง'
>>>>>>> origin/thai-lang
=======
          val => val !== null && val !== '' || 'กรุณาพิมพ์อายุของคุณนะครับ',
          val => val > 0 && val < 100 || 'กรุณาพิมพ์อายุที่ถูกต้องนะจ๊ะ '
>>>>>>> 523a4c6275a2f0a6211c0e499de14f4832fef794
        ]"
      />

      <q-toggle v-model="accept" label="ยอมรับ" />


      <q-toggle v-model="accept" label="ยอมรับ" />

      <div>
        <q-btn label="ยืนยัน" type="submit" color="primary"/>
        <q-btn label="เริ่มใหม่" type="reset" color="primary" flat class="q-ml-sm" />
        <q-btn label="ยืนยัน" type="submit" color="primary"/>
        <q-btn label="เริ่มใหม่" type="reset" color="primary" flat class="q-ml-sm" />
      </div>
    </q-form>


  </div>
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
            message: 'คุณจำเป็นต้องยอมรับ'
          })
        }
        else {
          $q.notify({
            color: 'green-4',
            textColor: 'white',
            icon: 'cloud_done',
            message: 'ข้อมูลได้รับการยืนยัน'
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