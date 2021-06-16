<template>
  <div class="flex w-full h-20">
    <div
      class="
        w-full
        md:w-max
        flex
        md:flex-shrink-0
        items-center
        border-b
        h-full
        px-5
        lg:px-14
        mx-4
      "
    >
      <img src="./../assets/images/icons/hamburger.svg" class="ml-1" />
      <img src="./../assets/images/logo.png" class="ml-12" />
      <span class="ml-5 text-3/2xl">CMS</span>
    </div>
    <div
      class="
        w-full
        h-full
        items-center
        justify-end
        border-b
        mx-4
        hidden
        md:flex
      "
    >
      <SearchField />
      <ul class="items-center text-base mr-6 hidden xl:flex">
        <li class="mx-3">
          <router-link to="/"><span>Pages</span></router-link>
        </li>
        <li class="mx-3">
          <router-link to="/"><span>Directory</span></router-link>
        </li>
        <li class="mx-3">
          <router-link to="/" class="flex items-center">
            <span>Content</span>
            <img src="../assets/images/icons/caret.svg" class="ml-3" />
          </router-link>
        </li>
        <li class="mx-3">
          <router-link to="/" class="flex items-center">
            <span>Team</span>
            <img src="../assets/images/icons/caret.svg" class="ml-3" />
          </router-link>
        </li>
        <li class="mx-3">
          <router-link to="/" class="flex items-center">
            <span>Templates</span>
            <img src="../assets/images/icons/caret.svg" class="ml-3" />
          </router-link>
        </li>
        <li class="mx-3">
          <router-link to="/"><span>Settings</span></router-link>
        </li>
      </ul>
      <button
        class="
          w-12
          h-12
          flex
          xl:hidden
          box-content
          flex-shrink-0
          items-center
          justify-center
          bg-blue-100
          mr-5
          rounded-lg
          border border-lightprimary
          relative
        "
      >
        <i class="fa fa-bars text-primary text-2xl"></i>
      </button>

      <button
        class="
          w-12
          h-12
          flex
          box-content
          flex-shrink-0
          items-center
          justify-center
          bg-blue-100
          mr-5
          rounded-lg
          border border-lightprimary
          relative
        "
      >
        <span
          class="
            w-3
            h-3
            absolute
            bg-red-500
            block
            top-2
            right-2
            rounded-full
            border-2
            box-content
          "
        ></span>
        <img src="./../assets/images/icons/chat.svg" />
      </button>
      <button
        class="
          w-12
          h-12
          flex
          box-content
          items-center
          justify-center
          bg-blue-100
          mr-5
          flex-shrink-0
          rounded-lg
          border border-lightprimary
        "
      >
        <img src="./../assets/images/icons/document.svg" />
      </button>
      <div class="flex-shrink-0">
        <img
          src="./../assets/images/profile.png"
          class="w-10 h-10 rounded-full"
        />
      </div>
    </div>
  </div>
</template> 

<script>
import SearchField from "../components/SearchField.vue";

export default {
  name: "Header",
  components: {
    SearchField,
  },
};
</script>
