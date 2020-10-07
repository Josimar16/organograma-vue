<style src="./style.css"></style>
<template>
  <div>
    <input type="checkbox" id="opcao" name="Modo colaborador" v-model="opcao" />
    <label for="opcao"> {{ opcao ? "Modo cargo" : "Modo colaborador" }}</label>
    <organization-chart :datasource="dados" :pan="true" :zoom="true">
      <template slot-scope="{ nodeData }">
        <div class="container">
          <img
            v-if="opcao"
            src="https://avatars3.githubusercontent.com/u/49077388?s=400&u=551a7010f9fc91859229f0d600481a2b2ca118a6&v=4"
            alt="profile"
          />
          <span v-if="opcao">{{ nodeData.name }}</span>
          <div v-else>
            <h4>{{ nodeData.cargo }}</h4>
            <hr />
          </div>
        </div>
      </template>
    </organization-chart>
  </div>
</template>
<script>
import OrganizationChart from "vue-organization-chart";
import "vue-organization-chart/dist/orgchart.css";

export default {
  components: {
    OrganizationChart,
  },
  data: () => ({
    opcao: false,
    dados: {
      id: 1,
      name: "Josimar Martins Pereira Junior",
      cargo: "CEO",
      children: [
        {
          id: 2,
          name: "Josimar Martins Pereira Junior",
          cargo: "Diretor",
          children: [],
        },
        {
          id: 3,
          name: "Josimar Martins Pereira Junior",
          cargo: "Diretor",
          children: [
            {
              id: 5,
              name: "Josimar Martins Pereira Junior",
              cargo: "Gerente",
              children: [],
            },
            {
              id: 6,
              name: "Josimar Martins Pereira Junior",
              cargo: "Gerente",
              children: [
                {
                  id: 10,
                  name: "Josimar Martins Pereira Junior",
                  cargo: "Coordenador",
                  children: [],
                },
              ],
            },
            {
              id: 7,
              name: "Josimar Martins Pereira Junior",
              cargo: "Gerente",
              children: [],
            },
          ],
        },
        {
          id: 4,
          name: "Josimar Martins Pereira Junior",
          cargo: "Diretor",
          children: [
            {
              id: 8,
              name: "Josimar Martins Pereira Junior",
              cargo: "Gerente",
              children: [
                {
                  id: 9,
                  name: "Josimar Martins Pereira Junior",
                  cargo: "Coordenador",
                  children: [],
                },
              ],
            },
          ],
        },
      ],
    },
  }),
};
</script>