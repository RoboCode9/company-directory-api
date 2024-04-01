<script setup>
import { faker } from '@faker-js/faker'

// const firstname = faker.person.firstName()
// const lastname = faker.person.lastName()
// const fullname = faker.person.fullName({firstName: firstname, lastName: lastname})
// const job_title = faker.person.jobTitle()
// const bio = faker.lorem.lines(2)
// const username = faker.internet.userName({firstName: firstname, lastName: lastname}).toLowerCase()

const props = defineProps({
    employee: {
        type: Object,
        required: true,
        default: () => {
            return {
                _id: "66005572aea52ea80d39287a",
                userName: "iii555",
                firstName: "Frank",
                lastName: "Doe",
                title: "Tester2",
                quote: "Hi",
                __v: 0
            }
        },
    },
})

</script>

<template>
    <!-- {{ fullname }} <br /> -->
    <RouterLink :to="{name: 'CardDetails', params: {id: props.employee._id}}">
        <div class="border border-green-400 rounded-lg shadow bg-red-500 h-full">
            <img :src="faker.image.urlLoremFlickr({category: 'selfie'})" class="rounded-t-xl" />
            <div class="p-7">
                <p class="mb-2 text-3xl font-serif">{{ props.employee.firstName }} {{ props.employee.lastName }}</p>
                <p class="mb-3 font-sans text-blue-800">{{ props.employee.title }}</p>
                <p class="mb-3 font-sans text-blue-800">{{ props.employee.quote }}</p>
            </div>
        </div>
    </RouterLink>
</template>