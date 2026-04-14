<script setup>
import { ref } from 'vue'

const noticias = ref([
  { titulo: 'Vestibular 2025', descricao: 'Inscrições abertas até 30/11' },
  { titulo: 'Calendário Acadêmico', descricao: 'Confira as datas do semestre' },
  { titulo: 'Eventos', descricao: 'Semana de Engenharia começa dia 10' }
])

const atalhos = [
  { nome: 'Portal do Aluno', icone: '📚' },
  { nome: 'Biblioteca', icone: '📖' },
  { nome: 'Cardápio', icone: '🍽️' },
  { nome: 'Atendimento', icone: '💬' }
]
</script>

<template>
  <div class="container">
    <!-- Cabeçalho -->
    <header>
      <h1>🏫 Sigaa</h1>
      <p>Portal de Serviços Acadêmicos</p>
    </header>

    <!-- Barra de Atalhos (a melhoria!) -->
    <div class="atalhos">
      <div v-for="item in atalhos" :key="item.nome" class="card-atalho">
        <span class="icone">{{ item.icone }}</span>
        <span>{{ item.nome }}</span>
      </div>
    </div>

    <!-- Seção de Notícias/Destaques -->
    <section>
      <h2>📢 Destaques</h2>
      <div class="grid-noticias">
        <div v-for="noticia in noticias" :key="noticia.titulo" class="card-noticia">
          <h3>{{ noticia.titulo }}</h3>
          <p>{{ noticia.descricao }}</p>
          <button>Saiba mais →</button>
        </div>
      </div>
    </section>
  </div>
</template>

<style scoped>
.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 20px;
  font-family: sans-serif;
}

header {
  text-align: center;
  margin-bottom: 40px;
}

.atalhos {
  display: flex;
  gap: 20px;
  justify-content: center;
  margin-bottom: 50px;
}

.card-atalho {
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  color: white;
  padding: 20px 30px;
  border-radius: 12px;
  text-align: center;
  cursor: pointer;
  transition: transform 0.2s;
}

.card-atalho:hover {
  transform: translateY(-5px);
}

.icone {
  font-size: 32px;
  display: block;
  margin-bottom: 10px;
}

.grid-noticias {
  margin-top: 30px;
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 25px;
}

.card-noticia {
  background: #f8f9fa;
  padding: 20px;
  border-radius: 12px;
  border-left: 4px solid #667eea;
}

.card-noticia button {
  background: #667eea;
  color: white;
  border: none;
  padding: 8px 16px;
  border-radius: 10px;
  cursor: pointer;
  margin-top: 12px;
}

.card-noticia button:hover {
  background: #5a67d8;
}
</style>