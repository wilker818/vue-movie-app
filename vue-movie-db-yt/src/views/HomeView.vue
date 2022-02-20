<template>
  <div class="home">
    <div class="feature-card">
      <router-link to="/movie/tt0409591">
        <img
          src="https://img.elo7.com.br/product/zoom/1EDD5DB/big-poster-do-anime-naruto-tamanho-90x-0-cm-lo094-nerd.jpg"
          width="390"
          height="450"
          alt="Naruto Poster"
          class="featured-img"
        />
        <div class="detail">
          <h3>Naruto</h3>
          <p>Issso é um lorem do Naruto a onde eu tento fazer o possível</p>
        </div>
      </router-link>
    </div>
    <form @submit.prevent="" class="search-box">
      <input type="text" placeholder="Oque você Procura?" />
      <input type="submit" value="Procurar" />
    </form>

    <div class="movies-list"></div>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss">
.home {
  .feature-card {
    position: relative;

    .feature-img {
      display: block;
      width: 100%;
      height: 300px;
      object-fit: cover;

      position: relative;
      z-index: 0;
    }
  }

  .detail {
    position: absolute;
    left: 0;
    right: 0;
    bottom: 0;
    background-color: rgba(0, 0, 0, 0.6);

    h3 {
      color: #fff;
      margin-bottom: 16px;
    }

    p {
      color: #fff;
    }
  }
}
.search-box {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding: 16px;

  input {
    display: block;
    appearance: none;
    border: none;
    outline: none;
    background: none;
  }
  &[type="text"] {
    width: 100%;
    color: #fff;
    background-color: #496583;
    font-size: 20px;
    padding: 10px 16px;
    border-radius: 8px;
    margin-bottom: 15px;
    transition: 0.4s;

    &::placeholder {
      color: #f3f3f3;
    }

    &:focus {
      box-shadow: 0px 3px 6px rgba(0, 0, 0, 0.2);
    }
  }
}
</style>