<template>
  <div id="app">
    
    <div class="jumbotron jumbotron-fluid">
      <div class="container">
        <h1 class="display-4">Formulários no Vue</h1>
        <p class="lead">Treinando a manipulação de formulários</p>
      </div>
    </div>

    <div class="container">

      <div class="row">

        <!-- formulario -->
        <div class="col-sm-6">

          <h3>Preencha abaixo</h3>

          <form>

            <div class="form-group">
              <label>Nome:</label>
              <input 
                type="text" 
                class="form-control" 
                placeholder="Seu nome"
                v-model.trim="formulario.nome">
            </div>

            <div class="form-group">
              <label>Endereço de email:</label>
              <input 
                type="email" 
                class="form-control" 
                placeholder="Seu email"
                v-model.lazy.trim="formulario.email">
            </div>

            <div class="form-group">
              <label>Idade:</label>
              <input 
                type="number" 
                class="form-control" 
                placeholder="Sua idade"
                v-model.number="formulario.idade">
            </div>

            <div class="form-group">

              <p>Gênero:</p>

              <div class="form-check form-check-inline">
                <input 
                  type="radio" 
                  id="mas" 
                  name="genero"
                  class="form-check-input" 
                  value="Masculino" 
                  v-model="formulario.genero">
                <label class="form-check-label">Masculino</label>
              </div>

              <div class="form-check form-check-inline">
                <input 
                  type="radio" 
                  id="fem"
                  name="genero" 
                  class="form-check-input" 
                  value="Feminino" 
                  v-model="formulario.genero">
                <label class="form-check-label">Feminino</label>
              </div>

            </div>

            <div class="form-group">
              <label>Ocupação:</label>
              <select class="form-control" placeholder="Seu email" v-model="formulario.ocupacao">
                <option disabled>Selecione uma opção...</option>
                <option>Pensionista</option>
                <option>Funcionário Privado</option>
                <option>Dor Lar</option>
                <option>Profissional Liberal</option>
              </select>
            </div>  

            <div class="form-group">

              <p>Tecnologias:</p>

              <div class="form-check form-check-inline">
                <input 
                  type="checkbox" 
                  class="form-check-input" 
                  value="JavaScript" 
                  v-model="formulario.tecnologias">
                <label class="form-check-label">JavaScript</label>
              </div>

              <div class="form-check form-check-inline">
                <input 
                  type="checkbox" 
                  class="form-check-input" 
                  value="Vue JS" 
                  v-model="formulario.tecnologias">
                <label class="form-check-label">Vue JS</label>
              </div>

              <div class="form-check form-check-inline">
                <input 
                  type="checkbox" 
                  class="form-check-input" 
                  value="Vuex" 
                  v-model="formulario.tecnologias">
                <label class="form-check-label">Vuex</label>
              </div>

              <div class="form-check form-check-inline">
                <input 
                  type="checkbox" 
                  class="form-check-input" 
                  value="Vue Router" 
                  v-model="formulario.tecnologias">
                <label class="form-check-label">Vue Router</label>
              </div>

            </div>      

            <div class="form-group">
              <label>Resumo de perfil:</label>
              <textarea 
                v-model.lazy.trim="formulario.resumoPerfil"
                class="form-control" 
                placeholder="Conte-nos um pouco sobre você..."></textarea>
            </div>

            <div class="form-group">

              <div class="form-check form-check-inline">
                <input 
                  type="checkbox" 
                  class="form-check-input" 
                  v-model="formulario.receberNotificacao">
                <label class="form-check-label">Receber notificações por email</label>
              </div>

            </div>

            <button class="btn btn-secondary">Resetar</button>
            <button class="btn btn-success">Enviar</button>

          </form>

        </div>

        <!-- saida -->
        <div class="col-sm-6">

          <h3>Saída</h3>

          <div class="card">

            <div class="card-header">Dados</div>

            <ul class="list-group list-group-flush">
              <li class="list-group-item"><strong>Nome:</strong>{{ formulario.nome }}</li>
              <li class="list-group-item"><strong>Email:</strong> {{ formulario.email }}</li>
              <li class="list-group-item"><strong>Idade:</strong>{{ formulario.idade }}</li>
              <li class="list-group-item"><strong>Gênero:</strong> {{ formulario.genero }}</li>
              <li class="list-group-item"><strong>Ocupação:</strong> {{ formulario.ocupacao }} </li>
              <li class="list-group-item"><strong>Tecnologias:</strong> 
                {{ formulario.tecnologias}}
              </li>
              <li class="list-group-item"><strong>Biografia:</strong> 
                <pre>{{ formulario.resumoPerfil }}</pre>
              </li>
              
              <li class="list-group-item">
                <strong>Receber notificações?</strong> 
                {{ formulario.receberNotificacao ? 'Sim' : 'Não'}} 
              </li>

            </ul>

            <div class="card-header">Model</div>

            <div class="card-body">
              <pre><code> {{ {'nome': formulario } }} </code></pre>
            </div>

          </div>

        </div>

      </div>

    </div>

  </div>
</template>

<script>
export default {
  data(){
    return {
      formulario :{
        nome : '',
        email : '',
        idade : '',
        genero :'',
        ocupacao: '',
        tecnologias : [],
        resumoPerfil : '',
        receberNotificacao : false,
      }
    }
  }
}
</script>

<style scoped>
  .btn {
    margin-right: 5px;
  }
</style>