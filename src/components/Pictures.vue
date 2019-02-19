<template>
  <div>
    <template v-if="loading > 0">
      Loading
    </template>
    <template v-else>
      <ul>
        <li v-for="picture in allPictureses" :key="picture.id">
          <div class="card">
            <div class="image">
              <img :src="picture.url" />
            </div>

            <div class="container">
              <h4>{{ picture.name }}</h4>
            </div>
          </div>
        </li>
      </ul>
    </template>
  </div>
</template>

<script>
import gql from 'graphql-tag'

const picturesQuery = gql`
  query allPictures {
    allPictureses {
      id
      name
      url
    }
  }
`;

export default {
  data: () => ({
    allPictureses: [],
    loading: 0
  }),
  apollo: {
    allPictureses: picturesQuery
  },
}
</script>

<style>
  .card {
    display: flex;
    flex-direction: column;

    box-shadow: 0 4px 8px 0 rgba(0,0,0,0.2);
    transition: 0.3s;
  }

  .card:hover {
    box-shadow: 0 8px 16px 0 rgba(255,0,0,0.3);
  }

  .container {
    padding: 2px 16px;
  }

  ul {
    padding: 0 1rem;
    list-style-type: none;
  }

  li {
    margin-bottom: 1rem;
  }

  .image {
    border-radius: 5px 5px 0 0;
  }
</style>
