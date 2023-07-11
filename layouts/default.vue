<template>
  <v-app dark>
    <v-app-bar app color="primary" dark clipped-left clipped-right>
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>
      <v-toolbar-title>APP NAME & LOGO</v-toolbar-title>
      <v-spacer />
      <v-text-field
        dark
        v-model="search"
        clearable
        clear-icon="mdi-close"
        class="mt-6"
        prepend-inner-icon="mdi-magnify"
        dense
        outlined
        label="ຄົ້ນຫາ"
        placeholder="ຄົ້ນຫາ"
        solo-inverted
      />
      <v-spacer />
      <v-btn
        class="flexcol ml-2 mr-2"
        icon
        v-for="item in menuItems"
        :key="item.title"
        :to="item.path"
      >
        <v-icon> {{ item.icon }} </v-icon>
        <span class="mt-2">{{ item.title }}</span>
      </v-btn>
    </v-app-bar>

    <v-navigation-drawer app v-model="drawer" clipped>
      <v-list nav>
        <v-list-item
          v-for="(item, i) in category"
          :key="i"
          :to="item.to"
          router
          exact
          color="primary"
        >
          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-main style="background-color: rgb(235, 235, 235)">
      <Nuxt class="py-2 px-3" />
    </v-main>

    <v-navigation-drawer app right clipped width="450">
      <v-simple-table fixed-header height="600">
        <template v-slot:default>
          <thead>
            <tr>
              <th class="text-left primary--text secondary">Product Name</th>
              <th class="text-left primary--text secondary">Quantity</th>
              <th class="text-left primary--text secondary">Price</th>
            </tr>
          </thead>
          <tbody>
            <tr v-for="item in productItems" :key="item.name">
              <td class="font-weight-medium">{{ item.name }}</td>
              <td class="font-weight-medium">{{ item.qty }}</td>
              <td class="font-weight-medium">{{ item.price }}</td>
            </tr>
          </tbody>
        </template>
      </v-simple-table>
      <v-divider class="mx-4 primary"></v-divider>
      <v-list-item class="">
        <h2>ລວມລາຄາ:</h2>
        <v-spacer></v-spacer>
        <h2>560000 LAK</h2>
      </v-list-item>
      <v-divider class="mx-4 primary"></v-divider>
      <v-card-actions>
        <v-btn color="primary" block large > 
          <v-icon size="25" left> mdi-cash-100 </v-icon> ຊຳລະເງິນ
        </v-btn>
      </v-card-actions>
    </v-navigation-drawer>
  </v-app>
</template>

<script>
export default {
  name: 'DefaultLayout',
  data() {
    return {
      search: '',
      drawer: true,
      drawer_right: true,
      fixed: true,
      title: 'App name & Logo',
      category: [
        {
          title: 'ເສື້ອຢີນ',
          to: '/',
        },
        {
          title: 'ເສື້ອແຈ໋ກເກັດ',
          to: '/A',
        },
        {
          title: 'ກະເປົາເດີນທາງ',
          to: '/B',
        },
        {
          title: 'ກະເປົາຄາດເອິກ',
          to: '/C',
        },
      ],
      menuItems: [
        {
          title: 'Users',
          path: '',
          icon: 'mdi-account',
        },

        {
          title: 'Orders',
          path: '',
          icon: 'mdi-reorder-horizontal',
        },
        {
          title: 'history',
          path: '',
          icon: 'mdi-history',
        },
        {
          title: 'Help',
          path: '',
          icon: 'mdi-help-circle-outline',
        },

        {
          title: 'Logout',
          path: '',
          icon: 'mdi-logout',
        },
      ],
      productItems: [
        {
          name: 'ກະເປົາເດີນທາງ Happy BC ກາກີ',
          qty: 1,
          price: '169000',
        },
        {
          name: 'ເສື້ອແຈັກເກັດ GP ດຳ 3XL',
          qty: 1,
          price: '229000',
        },
        {
          name: 'ກະເປົາເດີນທາງ COME ແດງ',
          qty: 1,
          price: '189000',
        },
      ],
    }
  },
}
</script>

<style>
.flexcol .v-btn__content {
  display: flex;
  flex-direction: column;
}
span {
  text-transform: capitalize;
}
</style>
