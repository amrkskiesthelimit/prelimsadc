<script setup>
    import MainNav from '@/Components/MainNav.vue'
    import { ref } from 'vue';
    import { Link } from '@inertiajs/vue3';

    let width = ref('w-[250px]')
    let hide = ref(false)

    function toggleWidth() {
        if(width.value == 'w-[250px]') {
            width.value = 'w-[100px]'
            hide.value = true
        }else {
            width.value = ['w-[250px]']
            hide.value = false
        }
    }
</script>

<template>

<div class="flex min-h-screen">
    <div id="sidebar" class="p-6 duration-500 bg-gray-900" :class="width" style="position: relative;">
        <button class="text-xl text-white" @click="toggleWidth" style="position: absolute; right: 10px; top:10px">
            <i class="fa-solid fa-bars"></i>
        </button>
        <div id="branding" :hidden="hide">
            <img src="data:image/jpeg;base64,/9j/4AAQSkZJRgABAQAAAQABAAD/2wCEABsbGxscGx4hIR4qLSgtKj04MzM4PV1CR0JHQl2NWGdYWGdYjX2Xe3N7l33gsJycsOD/2c7Z//////////////8BGxsbGxwbHiEhHiotKC0qPTgzMzg9XUJHQkdCXY1YZ1hYZ1iNfZd7c3uXfeCwnJyw4P/Zztn////////////////CABEIAP0A9gMBIgACEQEDEQH/xAAaAAEAAgMBAAAAAAAAAAAAAAAAAgMBBQYE/9oACAEBAAAAAOlACnT67xpbDcbEAAAazmoAbbpMgAAeLksAG76AAADkPG9W856oHZekAAPLxzZb95eZwG76AAAY03PezpR4NBAevr8gAI16LT9VeGPBT79N4eyskACNbQU9CAPHznZrJADFRo7tkAHOdOW5AKsHjegAPL7jNoCNYVgAnkTmBVgKwATyM2gxUCsAFgLchGsEMABYCcwhAEMADMwSsCEARiAMzBKwIQBiAAlIErAhACMQGZZBKwI1gIYAzMCcwxUArxkYxKwC3IKsAxUZMM2gzaBGs8vi8TfAIaD1+z2WpzA8Wr8PhgOi2QM6HUC/2e/dWBoucAZ3O4kz59JrQHr7KZ4+MwAJeqdHnADfdEcrqQAAAEu6shwkQAAADpN5rOSAAAAHt7PnNEAAAAHb8p4wAAAA6Hz6YAAAAN/0PN6MAAAA6va//8QAGAEBAQEBAQAAAAAAAAAAAAAAAAIBAwT/2gAKAgIQAxAAAAAAJqbzWXNQAABm8+oBfOpAACLi83c0bnTkAAVHHvFga3O/mmwAqNzj359ACo9HnzZsDcqDl15dgDpy7cSbzQqdk59ePYA68uvEzZsKjcIvh6ADtx6cjNmwqNwzfP6c0Nzv56kzZsKnZDn049wqfR5gzZsNyoN3h259QZ6/Jgm80Ly50TXl7zTPRy7cgjedG52kAM3cADnUb0m8AAAAzeNdo0AAAAcbubwAAADN5b//xAA3EAACAQEFBQYFAwMFAAAAAAABAgMEAAURIDEQITBAURITIjNBcSMyUmKBFHKSFUOhQlNzorH/2gAIAQEAAT8A4c08MC9qVwtpr6OkMX5e0l4Vsms7ew3WJJOJ2I7xnFHKnqDhaK9auPVhIPutTXnTz4Kfhv0PL114LTeBN8v+FtJI8rl5GLMdSeBQ3m0OEc5Jj6+q2BBAIOIPKV1WKSHEeY25LEliSSSScSTwrprCCKZzuPl8pX1H6mpdh8g3JtpqOWp3jwx/XZaGmWJogmuretp4XgkMb/g9RmBIIIOBGhtSTipp45PXRvcclXS9zSTP64YD3bbQ0Pf4SS+X6D6rAAAADADZV0wqY8NHHymzKVJVgQQcCM1yy4PND1AcciTha+JPgxJ1fZRUv6mXf5a/NYAAADJWUIqPGhwktLFJC3ZkQqdoBJwAJPQbKCQx1kB6thYHHjk4bL4PjgH2G2BJAAxJOAFqaAU8KRj8nqczKrgqygjobPdlM+naT2Nv6QnrO9oKaKmBEY9ydTa8oBFMHUYK9oj2ZYj0dbetg2PFJw23v58X/Ha7Yu8qe2dIxjw6+LvaV+qeIWQYug+9f/bHYp4ZOGS+B44G+0i11phTl/rfh7jrpaKnKXhHD0kx/A35AceExxOSugM9OQB418S2o17FLAPsHEigP6yedugRMgOB4LHAckNMqngMd/JDTKDgc505kaZm0znXkkzPnOvJJrmfO3DGuddcz5zwxnXXM/AI4IHAXXM2nBbgL68BMx3jgtrsxyY7F14A3DOwwOcnAZccg1GcDE8Bhu26DE6WkraSL5p09hvtJfMA8uJ2tJfFU3yBEtRV8pqMJ5SwfcODK4jikc/6VJsl61qauH/cLJfX1wfxNkvWjfVmT3Fkngl+SZG9jtUevAnvGkp2KO5LDVVtJfQ/tQfzNpL1rX0cJ+wWeSSQ4u7N7nHLQVomURSH4g/7cC8qwSfAjOKg+I5Y6moi8uZ19jZL2rF1Kv7i0V+LpLB+VNopY5kDxuGU5rzvEoTBAf3vwQSCCDgbU16aJUfzsjpIvaRgw6jJNUwQeZIAfpG82qrxknBSPwJ/k8GjrJKOXtrvU/Oto5ElRXQgqwxByV9SKWmZx853JxFZkOKsQeoOFlr6xf7xPuAbG8qz/cH8RZ6upk3PM/EuWqwJpm90yXxP3lWYxpFzaO0bo6HBlIItDKs0UciaOoOyRxHG8h0RSx/FmYuzM2pJJ9zzlyT4xSwfQcRsveTsURHq7Bedu+fuKyFjoT2G9m2X5JjJBF0Utz1HP+opYZPUrv8AcWr5hPVzOpxXHBfYc9cc/nQM33i15Xd3GM0I+F6j6Oeo7nBTt1X4S2tr0u6GCPv4twL4FObO4WoLuhgEcx8chGz/xAAiEQEAAQQDAAIDAQAAAAAAAAABAgAQESADMDESQSIyUVL/2gAIAQIBAT8A1ZYrLcl1rg2i9Uvdj3pCpeux0BaZh2iZbJqX5Prbj9buhfk8NuP7u6F5/rtx+N3QumRKRNYmC7oacnmkH8jR0L4a5ciaHpWG7pGOfawXnAmVKDH0sC+FcfFhy3wUw/l4mXf4x/yUAbTMObQO6RktEwHemFqMvp7lxXya/8QAIhEBAAEEAgICAwAAAAAAAAAAASACEBExAAMwMkFRISJA/9oACAEDAQE/AIlOeYLY40/XjDLKo8VGpOnwrnlHqTHE1t1uSVbgsMW/V8y7dFyFV+rbLt+Lm4O79ftLt2XNwd3HCPBHUanLc3Bh1+0Kz9WBBh1BiDpgQWFNTS8Khsocrrz+CA3Z5fuZZ8xZ/gTzBb//2Q==" alt="User Logo"
                class="w-[170px] h-[170px] mx-auto  object-cover">
            <h1 class="my-6 text-3xl text-center text-white">Dumandan John Mark</h1>

        </div>
        <hr class="border-gray-600" :hidden="hide">


        <MainNav :hidden="hide"></MainNav>
    </div>
    <div id="container" class="flex-1">
        <slot />
    </div>
</div>

</template>
