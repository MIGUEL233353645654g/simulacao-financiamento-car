<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Simulação de Financiamento de Carros</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f9;
        }
        header {
            background-color: #007BFF;
            color: white;
            text-align: center;
            padding: 10px 0;
        }
        .container {
            max-width: 1000px;
            margin: 20px auto;
            padding: 20px;
            background-color: white;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        .car-list {
            display: flex;
            flex-wrap: wrap;
            gap: 20px;
        }
        .car-item {
            flex: 1 1 calc(50% - 20px);
            background-color: #f0f0f0;
            border-radius: 8px;
            padding: 10px;
            box-shadow: 0 0 5px rgba(0, 0, 0, 0.1);
        }
        .car-item h3 {
            margin: 0 0 10px;
        }
        .car-item p {
            margin: 5px 0;
        }
        .calculator {
            margin-top: 30px;
        }
        .calculator input {
            width: 100%;
            padding: 10px;
            margin: 5px 0;
            border: 1px solid #ccc;
            border-radius: 4px;
        }
        .calculator button {
            background-color: #007BFF;
            color: white;
            border: none;
            padding: 10px;
            width: 100%;
            border-radius: 4px;
            cursor: pointer;
        }
        .calculator button:hover {
            background-color: #0056b3;
        }
    </style>
</head>
<body>
    <header>
        <h1>Simulação de Financiamento de Carros</h1>
    </header>

    <div class="container">
        <h2>Carros Disponíveis</h2>
        <div class="car-list">
            <div class="car-item" id="car1">
                <h3>Fiat Strada</h3>
                <p><strong>Ano:</strong> 2023</p>
                <p><strong>Preço:</strong> R$ 85.000</p>
                <p><strong>Quilometragem:</strong> 10.000 km</p>
                <p><strong>Eficiência:</strong> 12 km/l (urbano) / 15 km/l (estrada)</p>
                <p><strong>Segurança:</strong> Airbag, ABS, controle de estabilidade</p>
                <p><strong>Espaço Interno:</strong> Médio, capacidade para 2 ocupantes adicionais</p>
                <p><strong>Tecnologia:</strong> Central multimídia, Bluetooth</p>
                <p><strong>Concorrentes:</strong> VW Saveiro, Chevrolet Montana</p>
                <p><strong>Vantagens Competitivas:</strong> Custo-benefício, robustez para trabalho</p>
                <button onclick="simulate(85000)">Simular Financiamento</button>
            </div>
            <div class="car-item" id="car2">
                <h3>Fiat Toro</h3>
                <p><strong>Ano:</strong> 2023</p>
                <p><strong>Preço:</strong> R$ 130.000</p>
                <p><strong>Quilometragem:</strong> 5.000 km</p>
                <p><strong>Eficiência:</strong> 11 km/l (urbano) / 14 km/l (estrada)</p>
                <p><strong>Segurança:</strong> Airbag, ABS, controle de tração</p>
                <p><strong>Espaço Interno:</strong> Grande, excelente para famílias</p>
                <p><strong>Tecnologia:</strong> Sistema de navegação, Apple CarPlay</p>
                <p><strong>Concorrentes:</strong> Chevrolet S10, Toyota Hilux</p>
                <p><strong>Vantagens Competitivas:</strong> Conforto, espaço interno, tecnologia avançada</p>
                <button onclick="simulate(130000)">Simular Financiamento</button>
            </div>
            <div class="car-item" id="car3">
                <h3>Volkswagen Polo</h3>
                <p><strong>Ano:</strong> 2024</p>
                <p><strong>Preço:</strong> R$ 95.000</p>
                <p><strong>Quilometragem:</strong> 0 km (novo)</p>
                <p><strong>Eficiência:</strong> 13 km/l (urbano) / 16 km/l (estrada)</p>
                <p><strong>Segurança:</strong> Airbag, ABS, sensor de estacionamento</p>
                <p><strong>Espaço Interno:</strong> Compacto, confortável para 4 ocupantes</p>
                <p><strong>Tecnologia:</strong> Central multimídia, conectividade</p>
                <p><strong>Concorrentes:</strong> Fiat Argo, Honda Fit</p>
                <p><strong>Vantagens Competitivas:</strong> Eficiência de combustível, tecnologia moderna</p>
                <button onclick="simulate(95000)">Simular Financiamento</button>
            </div>
            <div class="car-item" id="car4">
                <h3>Chevrolet Onix</h3>
                <p><strong>Ano:</strong> 2024</p>
                <p><strong>Preço:</strong> R$ 92.000</p>
                <p><strong>Quilometragem:</strong> 0 km (novo)</p>
                <p><strong>Eficiência:</strong> 14 km/l (urbano) / 17 km/l (estrada)</p>
                <p><strong>Segurança:</strong> Airbag, ABS, controle de estabilidade</p>
                <p><strong>Espaço Interno:</strong> Compacto, adequado para 4 ocupantes</p>
                <p><strong>Tecnologia:</strong> Tela de 7” com Android Auto e Apple CarPlay</p>
                <p><strong>Concorrentes:</strong> VW Polo, Hyundai HB20</p>
                <p><strong>Vantagens Competitivas:</strong> Ótima eficiência de combustível, preço competitivo</p>
                <button onclick="simulate(92000)">Simular Financiamento</button>
            </div>
            <div class="car-item" id="car5">
                <h3>Toyota Yaris</h3>
                <p><strong>Ano:</strong> 2023</p>
                <p><strong>Preço:</strong> R$ 105.000</p>
                <p><strong>Quilometragem:</strong> 8.000 km</p>
                <p><strong>Eficiência:</strong> 12 km/l (urbano) / 15 km/l (estrada)</p>
                <p><strong>Segurança:</strong> Airbag, ABS, controle de estabilidade</p>
                <p><strong>Espaço Interno:</strong> Médio, bom para 4-5 ocupantes</p>
                <p><strong>Tecnologia:</strong> Central multimídia, navegação GPS</p>
                <p><strong>Concorrentes:</strong> Honda Fit, Hyundai HB20</p>
                <p><strong>Vantagens Competitivas:</strong> Durabilidade, segurança, baixo custo de manutenção</p>
                <button onclick="simulate(105000)">Simular Financiamento</button>
            </div>
            <div class="car-item" id="car6">
                <h3>Toyota Corolla</h3>
                <p><strong>Ano:</strong> 2023</p>
                <p><strong>Preço:</strong> R$ 150.000</p>
                <p><strong>Quilometragem:</strong> 7.000 km</p>
                <p><strong>Eficiência:</strong> 11 km/l (urbano) / 14 km/l (estrada)</p>
                <p><strong>Segurança:</strong> Airbag, ABS, assistente de faixa</p>
                <p><strong>Espaço Interno:</strong> Grande, conforto para 5 ocupantes</p>
                <p><strong>Tecnologia:</strong> Tela de 8” com conectividade avançada</p>
                <p><strong>Concorrentes:</strong> Honda Civic, VW Jetta</p>
                <p><strong>Vantagens Competitivas:</strong> Confiabilidade, conforto, revenda</p>
                <button onclick="simulate(150000)">Simular Financiamento</button>
            </div>
            <div class="car-item" id="car7">
                <h3>Hyundai HB20</h3>
                <p><strong>Ano:</strong> 2024</p>
                <p><strong>Preço:</strong> R$ 89.000</p>
                <p><strong>Quilometragem:</strong> 0 km (novo)</p>
                <p><strong>Eficiência:</strong> 13 km/l (urbano) / 16 km/l (estrada)</p>
                <p><strong>Segurança:</strong> Airbag, ABS, câmera de ré</p>
                <p><strong>Espaço Interno:</strong> Compacto, bom para 4 ocupantes</p>
                <p><strong>Tecnologia:</strong> Conectividade com smartphones</p>
                <p><strong>Concorrentes:</strong> Chevrolet Onix, Fiat Argo</p>
                <p><strong>Vantagens Competitivas:</strong> Preço acessível, boa eficiência</p>
                <button onclick="simulate(89000)">Simular Financiamento</button>
            </div>
            <div class="car-item" id="car8">
                <h3>Honda Civic</h3>
                <p><strong>Ano:</strong> 2023</p>
                <p><strong>Preço:</strong> R$ 145.000</p>
                <p><strong>Quilometragem:</strong> 6.000 km</p>
                <p><strong>Eficiência:</strong> 11 km/l (urbano) / 13 km/l (estrada)</p>
                <p><strong>Segurança:</strong> Airbag, ABS, controle de tração</p>
                <p><strong>Espaço Interno:</strong> Grande, confortável para 5 ocupantes</p>
                <p><strong>Tecnologia:</strong> Central multimídia com GPS</p>
                <p><strong>Concorrentes:</strong> Toyota Corolla, VW Jetta</p>
                <p><strong>Vantagens Competitivas:</strong> Estilo esportivo, tecnologia avançada</p>
                <button onclick="simulate(145000)">Simular Financiamento</button>
            </div>
            <div class="car-item" id="car9">
                <h3>BYD Seal</h3>
                <p><strong>Ano:</strong> 2024</p>
                <p><strong>Preço:</strong> R$ 190.000</p>
                <p><strong>Quilometragem:</strong> 0 km (novo)</p>
                <p><strong>Eficiência:</strong> 10 km/l (urbano) / 13 km/l (estrada)</p>
                <p><strong>Segurança:</strong> Airbag, ABS, controle de tração</p>
                <p><strong>Espaço Interno:</strong> Grande, ideal para 5 ocupantes</p>
                <p><strong>Tecnologia:</strong> Avançada, painel digital</p>
                <p><strong>Concorrentes:</strong> Tesla Model 3, BMW i4</p>
                <p><strong>Vantagens Competitivas:</strong> Tecnologia inovadora, desempenho elétrico</p>
                <button onclick="simulate(190000)">Simular Financiamento</button>
            </div>
            <div class="car-item" id="car10">
                <h3>Honda HR-V</h3>
                <p><strong>Ano:</strong> 2023</p>
                <p><strong>Preço:</strong> R$ 135.000</p>
                <p><strong>Quilometragem:</strong> 5.000 km</p>
                <p><strong>Eficiência:</strong> 12 km/l (urbano) / 15 km/l (estrada)</p>
                <p><strong>Segurança:</strong> Airbag, ABS, assistente de partida em rampa</p>
                <p><strong>Espaço Interno:</strong> Médio, versátil para família</p>
                <p><strong>Tecnologia:</strong> Central multimídia com GPS</p>
                <p><strong>Concorrentes:</strong> Jeep Renegade, Nissan Kicks</p>
                <p><strong>Vantagens Competitivas:</strong> Versatilidade, design moderno</p>
                <button onclick="simulate(135000)">Simular Financiamento</button>
            </div>
        </div>

        <div class="calculator">
            <h2>Simulador de Financiamento</h2>
            <label for="price">Preço do Carro (R$):</label>
            <input type="number" id="price" placeholder="Insira o preço do carro" readonly>
            
            <label for="entry">Entrada (R$):</label>
            <input type="number" id="entry" placeholder="Insira o valor da entrada">

            <label for="months">Número de Parcelas:</label>
            <input type="number" id="months" value="60" placeholder="Insira o número de parcelas">
            
            <label for="rate">Taxa de Juros Mensal (%):</label>
            <input type="number" id="rate" value="1.5" placeholder="Insira a taxa de juros">

            <button onclick="calculate()">Calcular Parcelas</button>
            <h3 id="result"></h3>
        </div>
    </div>

    <script>
        function simulate(price) {
            document.getElementById('price').value = price;
        }

        function calculate() {
            const price = parseFloat(document.getElementById('price').value);
            const entry = parseFloat(document.getElementById('entry').value);
            const months = parseInt(document.getElementById('months').value);
            const rate = parseFloat(document.getElementById('rate').value) / 100;

            if (isNaN(price) || isNaN(entry) || isNaN(months) || isNaN(rate)) {
                alert("Por favor, preencha todos os campos corretamente.");
                return;
            }

            const financedAmount = price - entry;
            const monthlyPayment = (rate * Math.pow(1 + rate, months) * financedAmount) / (Math.pow(1 + rate, months) - 1);

            document.getElementById('result').innerText = `Parcela Mensal: R$ ${monthlyPayment.toFixed(2)}`;
        }
    </script>
</body>
</html>
