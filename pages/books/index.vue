<template>
  <v-row>
    <v-col cols="12" class="text-right">

      <v-btn
        depressed
        color="primary"
        :to="'/books/new'"
      >
        Add Book
        <v-icon>mdi-plus</v-icon>
      </v-btn>
    </v-col>
    <v-col cols="12">
      <v-data-table
        :headers="headers"
        :items="dataBuku"
        :items-per-page="5"
        class="elevation-1"
      >
        <template v-slot:[`item.actions`]="{ item }">
          <v-btn class="mx-2" fab dark small color="primary" @click="editBook(item)">
            <v-icon>mdi-pencil</v-icon>
          </v-btn>
          <v-btn class="mx-2" fab dark small color="primary" @click="deleteBook(item)">
            <v-icon>mdi-trash-can</v-icon>
          </v-btn>
        </template>
      </v-data-table>
    </v-col>
  </v-row>
</template>

<script>
export default {
  name: 'InspirePage',
  data() {
    return {
      headers: [
        {
          text: 'Judul',
          align: 'start',
          sortable: false,
          value: 'judul',
        },
        { text: 'Penerbit', value: 'penerbit' },
        { text: 'Pengarang', value: 'pengarang' },
        { text: 'Tahun Terbit', value: 'tahun_terbit' },
        { text: '', value: 'actions' },
      ],
      dataBuku: [
        {
          _id: "asdasdasd1231231",
          judul: 'Frozen Yogurt',
          penerbit: "Bocil Epep",
          pengarang: "Habib Ganteng",
          tahun_terbit: "29-06-2022",
        },
      ],
    }
  },
  methods: {
    editBook(v){
      this.$router.push('/books/'+v._id)
    },
    deleteBook(v){}
  },
}
</script>
