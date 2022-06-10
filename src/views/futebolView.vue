<script>
import { v4 as uuidv4 } from  'uuid' ;
export default {
  data() {
    return {
      futebol: [
        {
          id: "da634ece-c98b-4e73-8732-66d81005fc27",
          nome: "futebol 1",
          time: "Time 1",
        },
        {
          id: "15a404de-4a33-40cb-92f5-b9518adea28e",
          nome: "futebol 2",
          time: "Time 2",
        },
        {
          id: "a49011ab-dc27-4dc8-a309-9ad2c86ea0f2",
          nome: "futebol 3",
          time: "Time 3",
        },
        {
          id: "724f5e50-6ee6-459f-af65-156016fa6e6e",
          nome: "futebol 4",
          time: "Time 4",
        },
        {
          id: "f6dbe8e9-9b85-489e-a0c5-3c539446a335",
          nome: "futebol 5",
          time: "Time 5",
        },
      ],
    };
  },
   methods: {
    salvar() {
      const novo_id = uuidv4();
      alert(novo_id + "" + this.novo_futebol );
      this.futebol.push({
      id: novo_id,
      nome: this.novo_futebol,
      });
    },
   },
};
</script>

<template>
  <div class="container">
    <div class="title">
      <h2>Gerenciamento de futebol</h2>
    </div>
    <div class="form-input">
      <input type="text" v-model="novo_jogadores" />
      <button @click="salvar">Salvar</button>
    </div>
    <div class="list-futebol">
      <table>
        <thead>
          <tr>
            <th>ID</th>
            <th>Nome</th>
            <th>Time</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="futebol in futebol" :key="futebol.id">
            <td>{{ futebol.id }}</td>
            <td>{{ futebol.nome }}</td>
            <td>{{ futebol.time }}</td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>
