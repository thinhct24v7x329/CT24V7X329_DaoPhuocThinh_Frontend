<script>
export default {
props: {
contact: { type: Object, required: true },
},
};
</script>
<template>
<div>
<div class="p-1">
<strong>Tên:</strong>
{{ contact.name }}
</div>
<div class="p-1">
<strong>E-mail:</strong>
{{ contact.email }}
</div>
<div class="p-1">
<strong>Địa chỉ:</strong>
{{ contact.address }}
</div>
<div class="p-1">
<strong>Điện thoại:</strong>
{{ contact.phone }}
</div>
<div class="p-1" v-if="contact.gender">
<strong>Giới tính:</strong>
{{ contact.gender === 'male' ? 'Nam' : contact.gender === 'female' ? 'Nữ' : contact.gender === 'other' ? 'Khác' : contact.gender }}
</div>
<div class="p-1" v-if="contact.hobbies">
<strong>Sở thích:</strong>
{{ contact.hobbies }}
</div>
<div class="p-1" v-if="contact.maritalStatus">
<strong>Tình trạng hôn nhân:</strong>
{{ contact.maritalStatus === 'single' ? 'Độc thân' : contact.maritalStatus === 'married' ? 'Kết hôn' : contact.maritalStatus === 'divorced' ? 'Ly hôn' : contact.maritalStatus }}
</div>
<div class="p-1">
<strong>Liên hệ yêu thích:&nbsp;</strong>
<i v-if="contact.favorite" class="fa-solid fa-check"></i>
<i v-else class="fa-solid fa-xmark"></i>
</div>
</div>
</template>
