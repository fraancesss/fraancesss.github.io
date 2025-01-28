
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
    width: 145px; 
    
}
.caixa {
            background-color: rgba(9, 1, 1, 0.5);
            display: flex;
            justify-content: center;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
            color: #ff1100 ;
            width: 200px;
            font-size: 30px;
           
           
        }
  
  
  </style>
  </body>
  <script>
    let { children } = $props();
  </script>
  
  
  <nav class="navbar navbar-expand-sm bg-body-tertiary">
    <div class="container-fluid">
        <a class="navbar-brand" href="/#">
            <img src="/medo.jpg" class="rounded-2" alt="5"  />
           
          </a>
      
         
      
    
      <div class="collapse navbar-collapse" id="navbarSupportedContent">
        <ul class="navbar-nav">
            <left>
  
          <div class="faca">
            <a class="nav-link" href="/ORDEM/01"> <img src="/conhecimento.jpg" alt="Logo" width="70" height="70" />
                <button class="btn btn-outline-primary" 
                onmouseover={entrando} onmouseout={saindo}
                onfocus={entrando}     onblur={saindo}>Pagina 1</button></a><br>

            <a class="nav-link" href="/ORDEM/02"> <img src="/morte.jpg" alt="Logo" width="70" height="70" />
                <button class="btn btn-outline-primary" 
                onmouseover={entrando} onmouseout={saindo}
                onfocus={entrando}     onblur={saindo}>Pagina 2</button></a><br>

            <a class="nav-link" href="/ORDEM/03"> <img src="/sangue.jpg" alt="Logo" width="70" height="70" />
                <button class="btn btn-outline-primary" 
                onmouseover={entrando} onmouseout={saindo}
                onfocus={entrando}     onblur={saindo}>Pagina 3</button></a><br>

            <a class="nav-link" href="/ORDEM/04"> <img src="/energia.jpg" alt="Logo" width="70" height="70" />
                <button class="btn btn-outline-primary" 
                onmouseover={entrando} onmouseout={saindo}
                onfocus={entrando}     onblur={saindo}>Pagina 4</button></a><br>
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

  // Gera o confete com canvas-confetti
  confetti({
      particleCount: 1000, // Quantidade de partículas
      spread: 500, // Abertura do confete
      origin: { y: 0.6 } // Origem do confete (altura relativa)
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
  
  
  
  
  
  
  