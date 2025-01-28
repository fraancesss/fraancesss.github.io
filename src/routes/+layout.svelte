<head>
   
    <style>
     
     body
     .faca {
    background-color: rgba(9, 1, 1, 0.5); 
    padding: 10px;
    border-radius: 10px;
    min-height: 5vh;
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
    color: #12520c ;
  }
  
  
  </style>
  </head>
  <script>
    let { children } = $props();
  </script>
  
  
  <nav class="navbar navbar-expand-sm bg-body-tertiary">
    <div class="container-fluid">
      <a class="navbar-brand" href="/#">
        <img src="/medo.jpg" alt="Logo" width="70" height="70" />
       
      </a>
      <button
        class="navbar-toggler"
        type="button"
        data-bs-toggle="collapse"
        data-bs-target="#navbarSupportedContent"
        aria-controls="navbarSupportedContent"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
      </button>
   
     
     
      <div class="collapse navbar-collapse" id="navbarSupportedContent">
        <ul class="navbar-nav">
  
  
          <div class="faca">
            <a class="nav-link" href="/#"> <img src="/conhecimento.jpg" alt="Logo" width="70" height="70" /></a>
            <a class="nav-link" href="/02"> <img src="/morte.jpg" alt="Logo" width="70" height="70" /></a>
            <a class="nav-link" href="/03"> <img src="/sangue.jpg" alt="Logo" width="70" height="70" /></a>
            <a class="nav-link" href="/04"> <img src="/energia.jpg" alt="Logo" width="70" height="70" /></a>
        </div>
        
          
         
        </ul>
      </div>
    </div>
  </nav>
  
  
  {@render children()}
  
  
  
  
  
  