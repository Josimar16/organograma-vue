<template>
  <organization-chart :datasource="dados" :pan="true" :zoom="true">
    <!--
      Estrutura do componente de organograma 
      <template slot-scope="{ nodeData }">
        <span>{{ nodeData.name }}</span>
      </template> 
    -->
  </organization-chart>
</template>
<script>
import OrganizationChart from "vue-organization-chart";
import "vue-organization-chart/dist/orgchart.css";

export default {
  components: {
    OrganizationChart,
  },
  data: () => ({
    dados: {
      id: 1,
      name: "Pai",
      children: [
        { id: 2, name: "Filho 1", children: [] },
        {
          id: 3,
          name: "Filho 2",
          children: [
            { id: 5, name: "Neto 1", children: [] },
            {
              id: 6,
              name: "Neto 2",
              children: [{ id: 7, name: "Bis Neto 1", children: [] }],
            },
            { id: 7, name: "Neto 3", children: [] },
          ],
        },
        {
          id: 4,
          name: "Filho 3",
          children: [
            {
              id: 8,
              name: "Neto 4",
              children: [{ id: 9, name: "Bis Neto 2", children: [] }],
            },
          ],
        },
      ],
    },
  }),
};
</script>