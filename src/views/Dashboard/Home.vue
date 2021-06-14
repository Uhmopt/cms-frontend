<template>
  <div class="px-16 py-10">
    <div class="flex items-center justify-between mb-9">
      <span class="text-2xl">Sites</span>
      <button
        class="w-48 px-1 box-content h-11 bg-primary text-sm rounded text-white"
      >
        Add Site
      </button>
    </div>
    <div class="flex flex-wrap -mx-4 mb-12">
      <SiteCard v-for="site in sites" :key="site.id" :site="site" />
    </div>

    <div>
      <p class="text-xl mb-9">Activity</p>
      <div class="flex items-center mb-4.5">
        <input type="text" placeholder="Search" class="w-56 h-12 box-content px-5 rounded border outline-none text-sm" />
        <button class="flex items-center border-0 bg-transparent ml-6">
          <span class="text-sm text-gray-500 mr-2.5">Sort</span>
          <img src="../../assets/images/icons/filter.svg" />
        </button>
        <button class="flex items-center border-0 bg-transparent ml-6">
          <span class="text-sm text-gray-500 mr-2.5">Filter</span>
          <img src="../../assets/images/icons/filter.svg" />
        </button>
      </div>
      <table class="w-full mb-16">
        <thead>
          <tr>
            <td 
              v-for="(col, index) in tableCols" 
              :key="index" class="font-medium text-xs py-5" 
              :class="index === tableCols.length - 1 && 'text-right'">
              {{col}}
            </td>
          </tr>
        </thead>
        <tbody>
          <tr v-for="row in rowData" :key="row.id" class="h-20 text-sm">
            <td class="pl-5">{{row.username}}</td>
            <td>{{row.sitename}}</td>
            <td><StaffCard :info="row.staff" /></td>
            <td>{{row.action}}</td>
            <td class="underline text-primary">{{row.name}}</td>
            <td class="text-right pr-5"><button><img src="../../assets/images/icons/more.svg" /></button></td>
          </tr>
        </tbody>
      </table>
      <div class="flex justify-center items-center">
        <paginate
          :page-count="15"
          :margin-pages="2"
          :page-range="6"
          :container-class="'flex'"
          :prev-link-class="'flex fa fa-angle-left w-8 h-8 items-center justify-center box-content rounded mx-1 text-lg mr-5'"
          :next-link-class="'flex fa fa-angle-right w-8 h-8 items-center justify-center box-content rounded mx-1 text-lg ml-5'"
          :prev-text="''"
          :next-text="''"
          :active-class="'bg-primary text-white'"
          :page-class="'w-8 h-8 flex items-center justify-center box-content rounded mx-1 text-sm'"
          :click-handler="clickCallback">
        </paginate>
      </div>
    </div>
  </div>
</template>

<script>
import 'font-awesome/css/font-awesome.min.css'
import Paginate from 'vuejs-paginate'
import SiteCard from '../../components/SiteCard.vue'
import StaffCard from '../../components/StaffCard.vue'
import DeskVantageAvatar from '../../assets/images/deskvantage.png'
import NikeAvatar from '../../assets/images/nike.png'
import ProfileNo1 from '../../assets/images/users/1.png'
import ProfileNo2 from '../../assets/images/users/2.png'
import ProfileNo3 from '../../assets/images/users/3.png'
import ProfileNo4 from '../../assets/images/users/4.png'
import ProfileNo5 from '../../assets/images/users/5.png'

export default {
  name: "Home",
  components: { SiteCard, StaffCard, Paginate },
  data: () => {
    return {
      tableCols: ['User name', 'Site Name', 'Staff', 'Action', 'Name', 'Action'],
      rowData: [
        {
          id: 1,
          username: '25/06/2020 04:55 PM',
          sitename: 'English Transcription',
          staff: {
            name: 'Serhii Movchan',
            role: 'Manager',
            avatar: ProfileNo2
          },
          action: 'Create New Task',
          name: 'Transcription',
        },
        {
          id: 2,
          username: '25/06/2020 04:55 PM',
          sitename: 'English Transcription',
          staff: {
            name: 'Serhii Movchan',
            role: 'Manager',
            avatar: ProfileNo3
          },
          action: 'Add New File',
          name: 'Logo.png',
        },
        {
          id: 3,
          username: '25/06/2020 04:55 PM',
          sitename: 'English Transcription',
          staff: {
            name: 'Serhii Movchan',
            role: 'Manager',
            avatar: ProfileNo2
          },
          action: 'Add New File',
          name: 'Logo.png',
        },
        {
          id: 4,
          username: '25/06/2020 04:55 PM',
          sitename: 'English Transcription',
          staff: {
            name: 'Serhii Movchan',
            role: 'Manager',
            avatar: ProfileNo2
          },
          action: 'Add New File',
          name: 'Logo.png',
        },
        {
          id: 5,
          username: '25/06/2020 04:55 PM',
          sitename: 'English Transcription',
          staff: {
            name: 'Serhii Movchan',
            role: 'Manager',
            avatar: ProfileNo2
          },
          action: 'Add New File',
          name: 'Logo.png',
        },
        {
          id: 6,
          username: '25/06/2020 04:55 PM',
          sitename: 'English Transcription',
          staff: {
            name: 'Serhii Movchan',
            role: 'Manager',
            avatar: ProfileNo2
          },
          action: 'Add New File',
          name: 'Logo.png',
        },
        {
          id: 7,
          username: '25/06/2020 04:55 PM',
          sitename: 'English Transcription',
          staff: {
            name: 'Serhii Movchan',
            role: 'Manager',
            avatar: ProfileNo2
          },
          action: 'Add New File',
          name: 'Logo.png',
        },
        {
          id: 8,
          username: '25/06/2020 04:55 PM',
          sitename: 'English Transcription',
          staff: {
            name: 'Serhii Movchan',
            role: 'Manager',
            avatar: ProfileNo2
          },
          action: 'Add New File',
          name: 'Logo.png',
        },
      ],
      sites: [
        {
          id: 1,
          name: "DeskVantage",
          updated: "6 weeks ago",
          avatar: DeskVantageAvatar,
          contributors: [
            ProfileNo1,
            ProfileNo2,
            ProfileNo3,
            ProfileNo4,
            ProfileNo5,
            ProfileNo5,
            ProfileNo5,
            ProfileNo5,
            ProfileNo5,
            ProfileNo5,
            ProfileNo5,
          ],
        },
        {
          id: 2,
          name: "Nike Pro",
          updated: "6 weeks ago",
          avatar: NikeAvatar,
          contributors: [
            ProfileNo1,
            ProfileNo2,
            ProfileNo3,
          ],
        },
      ],
    };
  },

};
</script>
