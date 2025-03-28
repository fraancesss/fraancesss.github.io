

<body>
    <style>
        body {
            background-image: url('https://images8.alphacoders.com/418/418516.jpg');
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
          color:#002de0;
          font-size:30px;
          font-weight: bold;


        }
    </style>
</body>

  
<script>
    let idPostagem = $state();
    let postagem = $state(null);
    let comentarios = $state([]);

    async function buscarPostagem() {
        try {
            let resposta = await fetch(`https://jsonplaceholder.typicode.com/posts/${idPostagem}`);
            postagem = await resposta.json();

            let resposta2 = await fetch(`https://jsonplaceholder.typicode.com/posts/${idPostagem}/comments`);
            comentarios = await resposta2.json();
        } catch (error) {
            console.error("Erro ao buscar os dados:", error);
        }
    }
</script>

<input placeholder="ID da postagem" type="number" bind:value={idPostagem} />
<button onclick={buscarPostagem}>Buscar postagem</button>

{#if postagem}
    <h1>{postagem.title}</h1>
    <p>{postagem.body}</p>
{/if}

<h2>Comentários</h2>
<ul>
    {#each comentarios as comentario}
        <li><strong>{comentario.name}</strong>: {comentario.body}</li>
    {/each}
</ul>



