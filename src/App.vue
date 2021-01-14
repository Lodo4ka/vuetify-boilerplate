<template>
  <v-app>
    <v-app-bar fixed app style="'z-index': '2 !important" elevate-on-scroll>
        <v-btn
        class="menu-button mr-2"
        fab
        small
        text
       >
        <v-icon dark>mdi-menu</v-icon>
      </v-btn>
      <v-spacer></v-spacer>
      <v-toolbar-items>
        <v-btn text > Registration </v-btn>
        <v-btn text> Log in </v-btn>
      </v-toolbar-items>
    </v-app-bar>
    <v-main>
       <v-container>
        <v-row>
          <v-col>
            <MaterialCard color="indigo" title="Login" text="Login in your profile">
              <v-col>
                <v-form ref="form" lazy-validation>
                  <v-text-field
                    validate-on-blur
                    label="Email"
                    type="email"
                  />
                  <v-text-field
                    label="Password"
                    type="password"
                  />
                </v-form>
              </v-col>

              <v-col cols="12" class="text-right">
                <v-btn
                  text
                >
                  Forgot your password?
                </v-btn>

                <v-btn
                  color="indigo"
                  dark
                >
                  Login
                </v-btn>
              </v-col>
            </MaterialCard>
          </v-col>
        </v-row>
      </v-container>
    </v-main>
  </v-app>
</template>

<script>

export default {
  components: {
     MaterialCard: () => import('@/components/MaterialCard.vue')
  },
  data() {
    return {
      headers: [
        {
          text: "Dessert (100g serving)",
          align: "start",
          sortable: false,
          select_filter: true,
          value: "name",
        },
        { text: "Calories", value: "calories", select_filter: true },
        { text: "Type", value: "obj.val", select_filter: true },
        { text: "Fat (g)", value: "fat" },
        { text: "Carbs (g)", value: "carbs" },
        { text: "Protein (g)", value: "protein" },
        { text: "Is Healthy?", value: "is_healthy", checkbox_filter: true },
        { text: "Iron (%)", value: "iron", select_filter: true },
        { text: "Tags", value: "tags", select_filter_many: true },
      ],
      desserts: null,
    };
  },
  mounted() {
    setTimeout(() => {
      this.setDeserts();
    }, 1000);
  },
  methods: {
    addItem() {
      this.desserts.push({
        name: "Frozen Yogurt" + Math.random().toString(32).slice(2, 5),
        obj: {
          val: 'Orange'
        },
        calories: 200,
        fat: 6.0,
        carbs: 24,
        protein: 4.0,
        is_healthy: false,
        iron: "1%",
        tags: ['cheap', 'tasty']
      });
    },
    setDeserts() {
      this.desserts = [
        {
          name: "Frozen Yogurt",
          obj: {
            val: 'Banana'
          },
          calories: 200,
          fat: 6.0,
          carbs: 24,
          protein: 4.0,
          is_healthy: true,
          iron: "1%",
          otherColumn: 4.0,
          tags: ['cheap', 'healthy']
        },
        {
          name: "Ice cream sandwich",
          obj: {
            val: 'Apple'
          },
          calories: 200,
          fat: 9.0,
          carbs: 37,
          protein: 4.3,
          is_healthy: true,
          iron: "1%",
          tags: ['healthy']
        },
        {
          name: "Eclair",
          obj: {
            val: 'Apple'
          },
          calories: 300,
          fat: 16.0,
          carbs: 23,
          protein: 6.0,
          is_healthy: true,
          iron: "7%",
          tags: ['junk-food', 'cheap']
        },
        {
          name: "Cupcake",
          obj: {
            val: 'Apple'
          },
          calories: 300,
          fat: 3.7,
          carbs: 67,
          protein: 4.3,
          is_healthy: true,
          iron: "8%",
          tags: ['junk-food', 'cheap']
        },
        {
          name: "Gingerbread",
          obj: {
            val: 'Apple'
          },
          calories: 400,
          fat: 16.0,
          carbs: 49,
          protein: 3.9,
          is_healthy: false,
          iron: "16%",
          tags: ['not-bad']
        },
        {
          name: "Jelly bean",
          obj: {
            val: 'Apple'
          },
          calories: 400,
          fat: 0.0,
          carbs: 94,
          protein: 0.0,
          is_healthy: false,
          iron: "0%",
          tags: ['junk-food']
        },
        {
          name: "Lollipop",
          obj: {
            val: 'Apple'
          },
          calories: 400,
          fat: 0.2,
          carbs: 98,
          protein: 0,
          is_healthy: false,
          iron: "2%",
          tags: ['junk-food', 'cheap', 'tasty']
        },
        {
          name: "Honeycomb",
          obj: {
            val: 'Apple'
          },
          calories: 400,
          fat: 3.2,
          carbs: 87,
          protein: 6.5,
          is_healthy: false,
          iron: "45%",
        },
        {
          name: "Donut",
          obj: {
            val: 'Apple'
          },
          calories: 500,
          fat: 25.0,
          carbs: 51,
          protein: 4.9,
          is_healthy: false,
          iron: "22%",
        },
        {
          name: "KitKat",
          obj: {
            val: 'Apple'
          },
          calories: 500,
          fat: 26.0,
          carbs: 65,
          protein: 7,
          is_healthy: false,
          iron: "6%",
        },
      ];
    },
  },
};
</script>
