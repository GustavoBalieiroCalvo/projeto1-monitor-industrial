# Monitor de Ativos Industriais

Projeto desenvolvido para praticar Python e SQL aplicados a sistemas industriais. O sistema simula leituras de sensores de equipamentos de fábrica, armazena os dados num banco SQLite, detecta anomalias e gera um relatório de status.

Nada de biblioteca externa — só Python puro e SQLite.

---

## O que ele faz

Equipamentos industriais como compressores e bombas precisam ser monitorados continuamente. Quando temperatura, pressão ou vibração saem do normal, você precisa saber antes que vire problema.

O sistema:
- Gera leituras simuladas de sensores para cada equipamento
- Armazena tudo num banco SQLite
- Compara os valores com thresholds e dispara alertas
- Exibe um relatório com o status atual de cada máquina

---

## Estrutura

```
industrial-asset-monitor/
├── database.py     # cria o banco e as tabelas
├── simulator.py    # cadastra equipamentos e gera leituras
├── alerts.py       # verifica thresholds e imprime alertas
├── report.py       # relatório de status por equipamento
└── main.py         # ponto de entrada
```

---

## Como rodar

Precisa só do Python 3.8+, sem instalar nada.

```bash
git clone https://github.com/seu-usuario/industrial-asset-monitor.git
cd industrial-asset-monitor
python main.py
```

Na primeira execução o banco é criado e os equipamentos são cadastrados automaticamente. Cada rodada gera um novo conjunto de leituras.

---

## Thresholds

Configurados em `alerts.py`:

| Sensor | Limite |
|---|---|
| Temperatura | 75.0 °C |
| Pressão | 8.0 bar |
| Vibração | 4.0 Hz |

---

## Exemplo de saída

```
Motor de simulação gerou dados

ALERTA — Compressor de Ar CP-01        | temperatura: 89.11° (máx: 75.00°)
ALERTA — Bomba Dosadora BD-03          | pressão: 9.18 bar (máx: 8.00 bar)

Bomba Dosadora BD-03       | 2026-06-24 15:51:40  | ALERTA
Compressor de Ar CP-01     | 2026-06-24 15:51:40  | OK
Misturador Industrial A    | 2026-06-24 15:51:39  | OK
```

---

## Autor

Gustavo Calvo — estudante de Engenharia da Computação na FESA e Inteligência Artificial na Univesp.
