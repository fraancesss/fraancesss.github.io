

<center>
    <div class="caixa1">
     
    <h1>OLAAA , Beleza filhote😶‍🌫️</h1>
  </div>
  </center>
  


  <div class="caixa2">


    <a href="/#"> <img src="/conhecimento.jpg" alt="Logo" width="70" height="70" /><button onclick={() => location.reload()}>
      Pagina 1
    </button><br>
      <div class="letra">
      </div></a>


<a href="/02"> <img src="/morte.jpg" alt="Logo" width="70" height="70" /><button class="btn btn-outline-primary"
  onmouseover={entrando} onmouseout={saindo}
  onfocus={entrando}     onblur={saindo}>Pagina 2</button><br>
  <div class="letra">
  </div></a>
 
    <a href="/03"> <img src="/sangue.jpg" alt="Logo" width="70" height="70" /><button class="btn btn-outline-primary"
      onmouseover={entrando} onmouseout={saindo}
      onfocus={entrando}     onblur={saindo}>Pagina 3</button><br>
      <div class="letra">
      </div></a>


      <a href="/04"> <img src="/energia.jpg" alt="Logo" width="70" height="70" /><button class="btn btn-outline-primary"
        onmouseover={entrando} onmouseout={saindo}
        onfocus={entrando}     onblur={saindo}>Pagina 4</button><br>
        <div class="letra">
       </div></a></div>


       
<div class="letra">
  {msg}</div>

  
  
  
  <body>
    <style>
      body {
        background-image: url('https://eskipaper.com/images/adventure-time-wallpaper-31.jpg');
        background-size: cover;
        background-position: center;
        background-attachment: fixed;
        height: 90vh;
      }
  
  
          .caixa1 {
              background-color: rgba(9, 1, 1, 0.5);
              display: flex;
              justify-content: center;
              padding: 20px;
              border-radius: 50px;
              box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
              color: #ff1100 ;
              width: 500px;
             
             
          }
          .caixa2 {
              background-color: rgba(9, 1, 1, 0.5);
              display: flex;
              justify-content: center;
              padding: 20px;
              border-radius: 10px;
              box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
              color: #ff1100 ;
              width: 250px;
             
             
          }
          .letra {
            color:#fac800;
            font-size:30px;
            font-weight: bold;
           
           
           
  
  
          }
  
  
  
  
  
  
    </style>
  </body>
  
  <script>
    let msg = $state('Passe o mouse algum botao para e clique para ir para as proximas paginas'),
        clicado = $state(false);
  
  
    function entrando() {
        msg = 'Agora clique no botão!';
    }
  
  
    function saindo() {
        if (clicado) msg = 'Você clicou no botão!';
        else msg = 'ESCOLHE CARAMBA';
        clicado = false;
    }
  
  
    function clicando() {
        clicado = true;
  
  
       
        confetti({
            particleCount: 1000,
            spread: 500,
            origin: { y: 0.6 }
        });
    }
  </script>
  
  
  <svelte:head>
    <script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.6.0/dist/confetti.browser.min.js"></script>
  </svelte:head>
  
  
  <style>
    button { transition: transform 0.3s ease; }
    button:hover { transform: scale(1.3); }
  </style>
  