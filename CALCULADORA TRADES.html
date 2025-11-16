<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Análise de Ações - Metodologia PEG</title>
    <style>
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: #f4f7f9;
            color: #333;
            padding: 20px;
        }
        .container {
            max-width: 800px;
            margin: 0 auto;
            background-color: #ffffff;
            padding: 30px;
            border-radius: 12px;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
        }
        h1 {
            color: #007bff;
            text-align: center;
            margin-bottom: 25px;
            border-bottom: 2px solid #007bff;
            padding-bottom: 10px;
        }
        .input-group {
            margin-bottom: 15px;
            display: flex;
            align-items: center;
            gap: 15px;
        }
        .input-group label {
            flex: 2;
            font-weight: 600;
            display: flex;
            align-items: center;
        }
        .input-group input {
            flex: 3;
            padding: 10px;
            border: 1px solid #ccc;
            border-radius: 6px;
            box-sizing: border-box;
            font-size: 16px;
        }
        .info-icon {
            cursor: pointer;
            color: #007bff;
            margin-left: 5px;
            font-weight: bold;
        }
        .info-tooltip {
            display: none;
            position: absolute;
            background-color: #333;
            color: white;
            padding: 8px;
            border-radius: 4px;
            font-size: 12px;
            z-index: 100;
            max-width: 250px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.3);
        }
        button {
            display: block;
            width: 100%;
            padding: 12px;
            background-color: #28a745;
            color: white;
            border: none;
            border-radius: 6px;
            font-size: 18px;
            cursor: pointer;
            margin-top: 20px;
            transition: background-color 0.3s;
        }
        button:hover {
            background-color: #218838;
        }
        .result-section {
            margin-top: 30px;
            padding: 20px;
            border: 1px solid #eee;
            border-radius: 8px;
            background-color: #f9f9f9;
        }
        .result-section h2 {
            text-align: center;
            color: #007bff;
            margin-top: 0;
        }
        .result-item {
            display: flex;
            justify-content: space-between;
            padding: 8px 0;
            border-bottom: 1px dashed #ddd;
        }
        .result-item strong {
            font-weight: 700;
        }
        /* Definições de Cores Visuais */
        .status-barato { color: #28a745; font-weight: bold; } /* Verde */
        .status-alerta { color: #ffc107; font-weight: bold; } /* Amarelo */
        .status-caro { color: #dc3545; font-weight: bold; } /* Vermelho */
        .status-muito-caro { color: #8b0000; font-weight: bold; } /* Vermelho Escuro */
    </style>
</head>
<body>

<div class="container">
    <h1>Ferramenta de Análise de Ações (Método PEG Ratio)</h1>
    <form id="analysisForm">
        <p>Insira os dados da Ação (últimos 12 meses):</p>

        <div class="input-group">
            <label for="currentPrice">Cotação Atual (P) (R$)</label>
            <input type="number" id="currentPrice" step="0.01" required value="8.49">
        </div>

        <div class="input-group">
            <label for="lpa">Lucro por Ação (LPA) (R$)</label>
            <input type="number" id="lpa" step="0.01" required value="1.69">
        </div>

        <div class="input-group">
            <label for="dy">
                DIVIDEND YIELD (D.Y.) (%) 
                <span class="info-icon" onmouseover="showTooltip(this, 'refere-se ao Rendimento de Dividendos, o indicador que verifica a performance da organização mediante os proventos que foram pagos aos acionistas ao longo dos últimos 12 meses do ano. Formula: (Dividendos Pagos / Preço da Ação) * 100.')" onmouseout="hideTooltip()">i</span>
            </label>
            <input type="number" id="dy" step="0.01" required value="8.64">
        </div>

        <div class="input-group">
            <label for="roe">
                ROE (Retorno sobre Patrimônio) (%) 
                <span class="info-icon" onmouseover="showTooltip(this, 'Mede a capacidade da empresa de gerar lucro a partir de seu patrimônio líquido. É essencial para calcular o Crescimento Sustentável. Formula: (Lucro Líquido / Patrimônio Líquido) * 100.')" onmouseout="hideTooltip()">i</span>
            </label>
            <input type="number" id="roe" step="0.01" required value="27.22">
        </div>

        <button type="submit">Analisar Ação</button>
    </form>

    <div id="results" class="result-section" style="display: none;">
        <h2>Resultados da Análise PEG Ratio</h2>
        
        <div class="result-item"><span>P/L (Preço/Lucro) Atual:</span> <strong id="plResult"></strong></div>
        <div class="result-item"><span>Crescimento Sustentável Esperado (g):</span> <strong id="gResult"></strong></div>
        <div class="result-item"><span>PEG Ratio (P/L sobre Crescimento):</span> <strong id="pegResult"></strong></div>
        
        <hr>
        
        <div class="result-item"><span>**Preço Aceitável (Justo) [PEG=1]:**</span> <strong id="priceJusto"></strong></div>
        <div class="result-item"><span>**Preço Caro (Sobrevalorizado) [PEG=3]:**</span> <strong id="priceCaro"></strong></div>
        
        <hr>

        <div class="result-item"><span>**STATUS DA AÇÃO:**</span> <strong id="statusFinal"></strong></div>
        
    </div>
</div>

<div id="tooltip" class="info-tooltip"></div>

<script>
    document.getElementById('analysisForm').addEventListener('submit', function(e) {
        e.preventDefault();
        runAnalysis();
    });

    function runAnalysis() {
        // 1. Coleta de Dados e Conversão para Decimal
        const P = parseFloat(document.getElementById('currentPrice').value);
        const LPA = parseFloat(document.getElementById('lpa').value);
        const DY_pct = parseFloat(document.getElementById('dy').value);
        const ROE_pct = parseFloat(document.getElementById('roe').value);
        
        const ROE = ROE_pct / 100;
        const DY = DY_pct / 100;

        // 2. Cálculos Iniciais
        const PL = P / LPA;

        // DPS é necessário para calcular o Payout
        const DPS = P * DY;
        const Payout = DPS / LPA;
        
        // Crescimento Sustentável (g): g = (1 - Payout) * ROE
        const retentionRate = 1 - Payout;
        // g em percentual para uso no PEG (conforme metodologia do vídeo)
        const g_pct = retentionRate * ROE * 100; 

        // 3. Cálculo do PEG Ratio
        const PEG = PL / g_pct;

        // 4. Determinação dos Preços Justo e Caro (Metodologia PEG)
        // Preço Aceitável (Justo): PEG = 1 => PL_justo = g
        const PL_justo = g_pct;
        const priceJusto = PL_justo * LPA;

        // Preço Caro (Sobrevalorizado): PEG = 3 => PL_caro = 3 * g
        const PL_caro = 3 * g_pct;
        const priceCaro = PL_caro * LPA;

        // 5. Determinação do Status Visual
        let statusText = '';
        let statusClass = '';

        if (P < priceJusto * 0.8) { // Abaixo de 80% do Justo
            statusText = `MUITO BARATA. Forte Margem de Segurança. (P < R$${priceJusto.toFixed(2)})`;
            statusClass = 'status-barato';
        } else if (P <= priceJusto) { // Entre 80% e o Preço Justo
            statusText = `BARATA / ACEITÁVEL. (P < R$${priceJusto.toFixed(2)})`;
            statusClass = 'status-barato';
        } else if (P > priceJusto && P < priceCaro) { // Entre Justo e Caro
            statusText = `ALERTA / PRÓXIMA DO CARO. (P > R$${priceJusto.toFixed(2)})`;
            statusClass = 'status-alerta';
        } else { // Acima do Preço Caro (PEG > 3)
            statusText = `CARA / SOBREVALORIZADA. (P > R$${priceCaro.toFixed(2)})`;
            statusClass = 'status-caro';
        }

        // 6. Exibição dos Resultados
        document.getElementById('plResult').textContent = PL.toFixed(2);
        document.getElementById('gResult').textContent = g_pct.toFixed(2) + '%';
        document.getElementById('pegResult').textContent = PEG.toFixed(3);
        
        document.getElementById('priceJusto').textContent = `R$ ${priceJusto.toFixed(2)}`;
        document.getElementById('priceCaro').textContent = `R$ ${priceCaro.toFixed(2)}`;
        
        const statusElement = document.getElementById('statusFinal');
        statusElement.textContent = statusText;
        statusElement.className = statusClass;
        
        document.getElementById('results').style.display = 'block';
    }

    // Funções para Tooltip (i)
    function showTooltip(element, text) {
        const tooltip = document.getElementById('tooltip');
        tooltip.textContent = text;
        
        const rect = element.getBoundingClientRect();
        tooltip.style.left = (rect.left + window.scrollX + 20) + 'px';
        tooltip.style.top = (rect.top + window.scrollY - 10) + 'px';
        tooltip.style.display = 'block';
    }

    function hideTooltip() {
        document.getElementById('tooltip').style.display = 'none';
    }
</script>

</body>
</html>
