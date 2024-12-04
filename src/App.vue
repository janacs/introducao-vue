<script setup>
import { ref } from "vue";
import coracaoOco from "./assets/coracao-borda.png"
import coracao from "./assets/coracao.png"



const sectionAtiva = ref(null);

const coracoes = ref([
  { id: 1, imagem: coracaoOco },
  { id: 2, imagem: coracaoOco },
  { id: 3, imagem: coracaoOco }
]);

// Função que muda apenas o coração específico
const mudarImagem = (index) => {
  coracoes.value[index].imagem = 
    coracoes.value[index].imagem === coracaoOco ? coracao : coracaoOco;
    
}

</script>

<template>
<header>
  <h1><span>Code</span>Lab</h1>
  <input type="text" placeholder="Pesquisar no blog">
</header>
<main>
  <div class="container-principal">
    <section :class="{ 'section-ativa': sectionAtiva === 1 }"
    @click="sectionAtiva = 1">
        <div class="data-coracao">
            <p class="data">17 de ago, 2024</p>
            <!-- diretivas -->
            <!-- para renderizar um dado da logica, se for em uma tag usaremos {{  }}-->
             <!-- para renderizar em atributos v-bind, (:) é o atalho do v-bind -->
            <img :src="coracoes[0].imagem"  alt="imagem dinâmica, coraçaõ completo e incompleto" @click="mudarImagem(0)">
        </div>
        <h3>O que é linguagem de programação? Conheça as principais!</h3>
        <p class="paragrafos">Uma das mais populares vertentes da tecnologia da informação, a área de programação segue tendo muita demanda de trabalho justamente pela velocidade com que dispositivos tecnológicos vêm avançando.</p>
    </section>
     <section :class="{ 'section-ativa': sectionAtiva === 2 }"
     @click="sectionAtiva = 2">
        <div class="data-coracao">
            <p class="data">12 de jul, 2024</p>
            <img :src="coracoes[1].imagem"  alt="imagem dinâmica, coraçaõ completo e incompleto" @click="mudarImagem(1)">
        </div>
        <h3>GitHub agora permite fazer login sem precisar de senha</h3>
        <p class="paragrafos">O GitHub anunciou nesta quarta-feira (12) o acesso a partir das passkeys, método de autenticação sem senhas. A novidade está disponível em uma versão beta pública e pode substituir a autenticação em dois fatores.</p>
    </section>
    <section :class="{'section-ativa': sectionAtiva === 3 }"
    @click="sectionAtiva = 3">
        <div class="data-coracao">
            <p class="data">21 de jun, 2024</p>
            <img :src="coracoes[2].imagem"  alt="imagem dinâmica, coraçaõ completo e incompleto" @click="mudarImagem(2)">
        </div>
        <h3>Por que os hiperlinks são azuis em sua maioria?</h3>
        <p class="paragrafos">Quem navega na internet, certamente já percebeu que ela conta com diversos recursos para tornar a nossa vida mais fácil. Entre essas opções podemos mencionar os hiperlinks – uma palavra ou termo clicável que direciona o leitor.</p>
    </section>
  </div>
</main>
</template>

<style scoped lang="scss">

main {
  display: flex;
  width: 100%;
  height: 80vh;
  flex-wrap: wrap;
  align-items: center;
  flex-direction: column;
  justify-content: center;
  
  @media (max-width: 580px) {
    height: 100%;
    margin-top: 30px;
    
  }
}

header {
  background-color: blanchedalmond;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 210px;
  background-color:  #1C1C1C;
  gap: 30px;

  @media (max-width: 580px) {
    height: 20vh;
   
  }

  span {
    color: #E07B67
  }

  h1 {
    font-weight: 400;
    font-size: 26px;
  }

  input {
    width: 50%;
    height: 30px;
    background-color: #202024;
    border: 2px solid #252529;
    border-radius: 4px;
    padding: 10px;
    font-family: "Inter", serif;
    
    @media (max-width: 580px) {
      width: 80%;
    }
  }
}

section {
  display: flex;
  flex-direction: column;
  width: 100%;
  height: 150px;
  padding: 0 20px;
  border: 1px solid #632b20;
  justify-content: center;
  background-color: #1C1C1C;
  border-radius: 8px;
  gap: 6px;

  @media (max-width: 580px) {
    padding: 10px;
    height: 200px;
    border: 1px solid #632b20;
  }

  h3 {
    font-size: 16px;
    font-weight: 400;
    margin: 10px 0;
    
  }

}

.section-ativa {
  border: 1px solid #E07B67;
}

.container-principal {
  display: flex;
  flex-direction: column;
  width: 50%;
  height: 100%;
  justify-content: center;
  align-items: center;
  gap: 20px;

  @media (max-width: 900px){
    width: 90%;
    gap: 30px;
    margin-bottom: 20px;
  }
}

.paragrafos {
  margin-bottom: 20px;
  font-family: "Inter", serif;
  line-height: 18px;
  font-size: 14px;
  font-weight: 200;
  color: #AFABB6;

}

.data {
  color: #E07B67;
  font-size: 12px;
  font-weight: 200;
  
}

.data-coracao {
  display: flex;
  justify-content: space-between;
  margin-top: 20px;

  img {
    width: 3%;
    cursor: pointer;

    img:hover {
      transform: scale(1.1);
    }

    @media (max-width: 580px) {
      width: 6%;
    }
  }
}
</style>