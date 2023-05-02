<template>
  <Page>
    <ActionBar title="Listado" />
    <StackLayout>
      <ListView for="item in items">
        <v-template>
          <StackLayout class="item">
            <Label :text="item.title" class="title" />
            <Label :text="item.description" class="description" />
          </StackLayout>
        </v-template>
      </ListView>
    </StackLayout>
  </Page>
</template>

<script>
export default {
  data() {
    return {
      items: [],
    };
  },
  mounted() {
    fetch('https://jsonplaceholder.typicode.com/posts')
      .then((response) => response.json())
      .then((data) => {
        this.items = data;
      });
  },
};
</script>
