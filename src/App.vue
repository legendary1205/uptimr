<template>
<ThemeSwitcher />
    <router-view />
</template>

<script>
import { setPageLocale } from "./util-frontend";
export default {
    created() {
        setPageLocale();
    },
};
</script>
import ThemeSwitcher from "@/components/ThemeSwitcher.vue";

export default {
  components: {
    ThemeSwitcher
  }
}
