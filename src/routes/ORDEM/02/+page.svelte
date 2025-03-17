<body>
    <style>
        body {
            background-image: url('https://images3.alphacoders.com/237/237345.jpg');
           
        }
        .bandeira {
            width: 30px;
            height: 20px;
            margin-right: 5px;
        }
        .CS {
            display: flex;
            align-items: center;
            gap: 5px;
        }
        .CS2 {
            display: flex;
            align-items:center;
            gap: 5px;
        }
        .caixa1 {
            background: rgba(227, 213, 23, 0.9);
            padding: 20px;
            border-radius: 10px;
            text-align: center;
            width: 600px;
            
        }
    </style>
</body>

<script>
    let moedas = [
        { nome: 'Dólar americano', código: 'USD', bandeira: 'https://flagcdn.com/w40/us.png' },
        { nome: 'Real brasileiro', código: 'BRL', bandeira: 'https://flagcdn.com/w40/br.png' },
        { nome: 'Euro', código: 'EUR', bandeira: 'https://flagcdn.com/w40/eu.png' },
        { nome: 'Libra esterlina', código: 'GBP', bandeira: 'https://flagcdn.com/w40/gb.png' },
        { nome: 'Iene japonês', código: 'JPY', bandeira: 'https://flagcdn.com/w40/jp.png' },
        { nome: 'Peso argentino', código: 'ARS', bandeira: 'https://flagcdn.com/w40/ar.png' }
    ];

    let código1 = $state(moedas[0].código);
    let código2 = $state(moedas[1].código);
    let valor1 = $state(0);
    let valor2 = $state(0);
    let moedaPadrao = $state({ rates: {} });

    function getBandeira(codigo) {
        return moedas.find(m => m.código === codigo)?.bandeira || '';
    }

    async function mudarMoeda() {
        try {
            const resposta = await fetch(`https://open.er-api.com/v6/latest/${código1}`);
            const dados = await resposta.json();
            if (dados.result === "success") {
                moedaPadrao = dados;
                converterDe();
            } else {
                console.error("Erro ao buscar dados da API", dados);
            }
        } catch (error) {
            console.error("Erro na requisição da API", error);
        }
    }

    function converterDe() {
        valor2 = (valor1 * (moedaPadrao.rates[código2] || 0)).toFixed(2);
    }

    function converterPara() {
        valor1 = (valor2 / (moedaPadrao.rates[código2] || 1)).toFixed(2);
    }

    function inverterMoedas() {
        [código1, código2] = [código2, código1];
        [valor1, valor2] = [valor2, valor1];
        mudarMoeda();
    }

    mudarMoeda();
</script>

<center>
<div class="caixa1">
    <h1 class="text-center">Cotação de moedas</h1>
    <div class="input-group">
        <div class="CS">
            <img class="bandeira" src={getBandeira(código1)} alt="Bandeira" />
            <select class="form-select" bind:value={código1} onchange={mudarMoeda}>
                {#each moedas as moeda}
                    <option value={moeda.código} title={moeda.nome}>{moeda.código}</option>
                {/each}
            </select>
        </div>
        <input placeholder="0,00" type="number" class="form-control w-25" oninput={converterDe} bind:value={valor1} />
        <br>
        <button class="btn btn-outline-secondary" type="button" onclick={inverterMoedas}>⇄</button>
        <br>
        <input placeholder="0,00" type="number" class="form-control w-25" oninput={converterPara} bind:value={valor2} />
        <div class="CS2">
            <img class="bandeira" src={getBandeira(código2)} alt="Bandeira" />
            <select class="form-select" bind:value={código2} onchange={converterPara}>
                {#each moedas as moeda}
                    <option value={moeda.código} title={moeda.nome}>{moeda.código}</option>
                {/each}
            </select>
        </div>
    </div>
    
    <div class="text-center mt-3">
        <p>Taxa de câmbio: 1 {código1} = {moedaPadrao.rates[código2] || 'N/A'} {código2}</p>
    </div>

    <div class="position-fixed bottom-0 end-0 m-3">
        <a href="https://www.exchangerate-api.com">Rates By Exchange Rate API</a>
    </div>
</div>
</center>