<template>
  <div class="mt-3">
    <h4>Thêm Liên hệ</h4>
    <ContactForm :contact="emptyContact" @submit:contact="submitContact" @delete:contact="deleteContact" />
  </div>
</template>

<script>
import ContactForm from "@/components/ContactForm.vue";
import ContactService from "@/services/contact.service";

export default {
  components: { ContactForm },
  data() {
    return {
      emptyContact: {
        name: "",
        email: "",
        address: "",
        phone: "",
        hobbies: "",
        maritalStatus: "",
        gender: "",
        favorite: false,
      },
    };
  },
  methods: {
    async submitContact(data) {
      try {
        await ContactService.create(data);
        alert("Liên hệ được thêm thành công.");
        this.$router.push({ name: "contactbook" });
      } catch (error) {
        console.error(error);
        alert("Có lỗi xảy ra khi thêm liên hệ");
      }
    },
    deleteContact() {
      // no-op for add page
    },
  },
};
</script>

<style scoped></style>
