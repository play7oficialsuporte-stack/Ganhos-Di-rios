<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Painel de Recompensas</title>
    <style>
        body { font-family: sans-serif; background-color: #1a1a2e; color: white; text-align: center; padding: 20px; }
        .balance-card { background: #16213e; padding: 20px; border-radius: 15px; margin-bottom: 20px; border: 1px solid #4e31aa; }
        .mission-card { background: #0f3460; padding: 15px; border-radius: 10px; margin-bottom: 10px; display: flex; justify-content: space-between; align-items: center; }
        .btn-go { background: #4e31aa; color: white; border: none; padding: 10px 20px; border-radius: 5px; cursor: pointer; text-decoration: none; font-weight: bold; }
        h1 { border-left: 5px solid #4e31aa; padding-left: 10px; display: inline-block; font-size: 1.2rem; }
    </style>
</head>
<body>

    <div class="balance-card">
        <p>Saldo Atual</p>
        <h2 id="saldo">R$ 0,00</h2>
    </div>

    <h1>Missões Disponíveis</h1>

    <div class="mission-card">
        <div>
            <strong>Missão 01</strong><br>
            <small>Ganhe R$ 1,50</small>
        </div>
        <button class="btn-go" onclick="doMission(1.50, 'https://installyourfiles.com/1879502')">IR</button>
    </div>

    <div class="mission-card">
        <div>
            <strong>Missão 02</strong><br>
            <small>Ganhe R$ 2,00</small>
        </div>
        <button class="btn-go" onclick="doMission(2.00, '#')">IR</button>
    </div>

    <div class="mission-card">
        <div>
            <strong>Missão 03</strong><br>
            <small>Ganhe R$ 3,50</small>
        </div>
        <button class="btn-go" onclick="doMission(3.50, '#')">IR</button>
    </div>

    <script>
        let currentBalance = 0;

        function doMission(valor, link) {
            if(link === '#') {
                alert('Esta missão ainda não possui um link configurado.');
                return;
            }
            window.open(link, '_blank');
            currentBalance += valor;
            document.getElementById('saldo').innerText = 'R$ ' + currentBalance.toFixed(2).replace('.', ',');
            alert('Missão iniciada! O saldo visual será atualizado.');
        }
    </script>
</body>
</html>
