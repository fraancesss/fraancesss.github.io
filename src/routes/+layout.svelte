

<body>
   
    <style>
     
     body
     .faca {
        
    background-color: rgba(9, 1, 1, 0.5); 
    padding: 10px;
    border-radius: 10px;
    min-height: 5vh;
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
    color: #12520c ;
    width: 180px;
  
      
}

.caixa {
        
        background-color: rgba(9, 1, 1, 0.5); 
        padding: 10px;
        border-radius: 10px;
        min-height: 5vh;
        box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
        color: #12520c ;
        width: 145px;
        display: flex;
            justify-content: center;          
    }
    .letra1 {
            color:#ff00ea;
            font-size:22px;
            font-weight: bold;
        
          }

  
  </style>
  </body>
  <script>
    let { children } = $props();
  </script>
  
  
  <nav class="navbar navbar-expand-sm bg-body-tertiary">
    <div class="container-fluid">
      <div class="caixa">
        <a class="navbar-brand" href="/#">
            <img src="/medo.jpg" class="rounded-2" alt="5"  />
           
          </a></div>
      
         
      
    
      <div class="collapse navbar-collapse" id="navbarSupportedContent">
        <ul class="navbar-nav">
            <left>
  
          <div class="faca">
            <div class="letra1">
            <p>Elementos</p>
          </div>
            

            <a class="nav-link" href="/ORDEM/02"> <img src="/morte.jpg" alt="Logo" width="70" height="70" />
                <button class="btn btn-outline-primary" onclick={clicando}
                onmouseover={entrando} onmouseout={saindo}
                onfocus={entrando}     onblur={saindo}>Medo</button></a>

               

            

            <a class="nav-link" href="/ORDEM/04"> <img src="/energia.jpg" alt="Logo" width="70" height="70" />
                <button class="btn btn-outline-primary" onclick={clicando}
                onmouseover={entrando} onmouseout={saindo}
                onfocus={entrando}     onblur={saindo}>Energia</button></a>
        </div>
        
    </left>
         
        </ul>
      </div>
    </div>
  </nav>
  <script module>
  let msg = $state('Passe o mouse sobre o botão e clique'),
  clicado = $state(false);

function entrando() {
  msg = 'Agora clique no botão!';
}

function saindo() {
  if (clicado) msg = 'Você clicou no botão e nao saiu da pagina!';
  else msg = 'CARAMBA ESCOLHE LOGO';
  clicado = false;
}

function clicando() {
  clicado = true;

  
  confetti({
      particleCount: 750, 
      spread: 500, 
      origin: { y: 0.6 } 
  });
}
</script >

<svelte:head>
<script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.6.0/dist/confetti.browser.min.js"></script>
</svelte:head>

<style>
button { transition: transform 0.3s ease; }
button:hover { transform: scale(1.3); }
</style>
  
  {@render children()}
  
  
  
  
  
  
  