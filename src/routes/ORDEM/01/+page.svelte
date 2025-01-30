<script>
  import { filmes, gêneros } from '$lib/ordem.js';

  let gênerosSelecionados = $state([]);
  let filtrados = $state(filmes.slice());

  function filtrarGenero(event) {
      if (event.target.checked) {
          gênerosSelecionados.push(event.target.value);
      } else {
          gênerosSelecionados.splice(gênerosSelecionados.indexOf(event.target.value), 1);
      }

      if (gênerosSelecionados.length == 0) {
          filtrados = filmes.slice();
      } else {
          filtrados = [];
          for (const filme of filmes) {
              for (const gênero of gênerosSelecionados) {
                  if (filme.gêneros.includes(gênero)) {
                      filtrados.push(filme);
                      break;
                  }
              }
          }
      }
  }
</script>


  {#each gêneros as gênero}
  <div class="genero">
      <div class="col">
          <div class="form-check form-check-inline">
              <input type="checkbox" oninput={filtrarGenero} class="form-check-input" id={gênero} value={gênero} />
              <label class="form-check-label" for={gênero}>{gênero}</label>
          </div>
        </div>
      </div>
  {/each}

<div class="row g-4">
  {#each filtrados as filme}
      <div class="col-md-6 col-xl-3">
          <div class="card h-100">
              <div class="row g-0">
                <div class="caixa1">
                  <div class="col-3 col-sm-4 d-flex align-items-center justify-content-center">
                      <img src={filme.imagem} class="img-fluid rounded-top" alt="capa do filme" style="max-height: 300px; object-fit: cover;" />
                  </div>
                  <div class="col-sm-8">
                    
                      <div class="card-body">
                          <h1 class="card-title">{filme.título}</h1>
                          <h3 class="card-subtitle mb-2 text-body-secondary">{filme.ano}</h3>
                          <p class="card-text">{filme.sinopse}</p>
                          <p class="card-text">
                              {#each filme.gêneros as gênero}
                              
                                  <span class="badge text-bg-secondary mx-2" >ELEMENTO:{gênero}</span><br>
                              {/each}
                              

                              <a href="{filme.referência}"><button class="btn btn-warning mt-1">Mais Informações</button></a>

                              
                          </p>
                        </div>
                      </div>
                  </div>
              </div>
          </div>
      </div>
  {/each}
</div>


<body>
 
  <style>
   
   body {
          background-image: url('https://eskipaper.com/images/adventure-time-wallpaper-31.jpg');
          background-size: cover;
          background-position: center;
          background-attachment: fixed;
          height: 100vh;
          overflow: auto;
      }
      .genero {
        background-color: rgba(32, 16, 16, 0.5);
    padding: 5px;
    border-radius: 30px;
    color: #ffffff;
    text-align: center;
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
    margin-bottom: 20px;
    width: 150px;
    font-weight: bold;
    display:inline-block;
          
      }
      .caixa1 {
       background-color: rgba(9, 1, 1, 0.5);
      display: flex;
      flex-wrap: wrap; /* Permite quebra de linha se necessário */
      justify-content: center;
      align-items: center;
      padding: 20px;
      border-radius: 50px;
      box-shadow: 0 4px 10px rgba(0, 0, 0, 0.3);
      color: #fac800;
      max-width: 800px;
      margin: 20px auto;
      font-size: 20px;
      font-weight: bold;
      text-align: center;

  }
      



 
  </style>
</body>



