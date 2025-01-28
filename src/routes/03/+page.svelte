<div class="caixa2">
    <a href="/#"> <img src="/conhecimento.jpg" alt="Logo" width="70" height="70" /><button class="btn btn-outline-primary" onclick={clicando}
        onmouseover={entrando} onmouseout={saindo}
        onfocus={entrando}     onblur={saindo}>Pagina 1</button><br>
      </a>
     
        <a href="/02"> <img src="/morte.jpg" alt="Logo" width="70" height="70" /><button class="btn btn-outline-primary"
            onmouseover={entrando} onmouseout={saindo}
            onfocus={entrando}     onblur={saindo}>Pagina 2</button><br>
          </a>


          <a href="/03"> <img src="/sangue.jpg" alt="Logo" width="70" height="70" /><button  class="btn btn-outline-primary" onclick={clicando}
            onmouseover={entrando} onmouseout={saindo}
            onfocus={entrando}     onblur={saindo}>
            Pagina 3
        </button><br>
            </a>
         
          <a href="/04"> <img src="/energia.jpg" alt="Logo" width="70" height="70" /><button class="btn btn-outline-primary"
            onmouseover={entrando} onmouseout={saindo}
            onfocus={entrando}     onblur={saindo}>Pagina 4</button><br>
            </a>
        </div>

<body>
    <style>
        body {
            background-image: url('https://wallpapercave.com/wp/wp10971695.jpg');
            background-size: cover;
            background-position: center;
            background-attachment: fixed;
            height: 90vh;
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
          color:#fa1100;
          font-size:30px;
          font-weight: bold;


        }
    </style>
</body>

<script>
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
</script>

<svelte:head>
    <script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.6.0/dist/confetti.browser.min.js"></script>
</svelte:head>

<div class="letra">
    
    <p>{msg}</p>
    
</div>


<style>
    button { transition: transform 0.3s ease; }
    button:hover { transform: scale(1.3); }
</style>
  
<center>
    <div class="caixa1">
     
    <h1>blood</h1>
  </div>
  </center>
