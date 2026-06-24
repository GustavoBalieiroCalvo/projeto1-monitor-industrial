# Monitor de Ativos Industriais

Sistema de monitoramento de ativos industriais desenvolvido em Python com banco de dados SQLite. Simula leituras de sensores de equipamentos de fábrica, detecta anomalias com base em thresholds configuráveis e gera relatórios de status em tempo real.

Projeto desenvolvido como parte de estudos em sistemas de manufatura e automação industrial.

---

## O problema

Em ambientes industriais, equipamentos como compressores, bombas e misturadores operam continuamente e precisam ser monitorados para evitar falhas. Sem um sistema centralizado, anomalias passam despercebidas até virarem parada de linha.

## A solução

O sistema coleta leituras simuladas de temperatura, pressão e vibração de cada equipamento, armazena no banco e dispara alertas quando algum valor ultrapassa o limite operacional. Um relatório consolidado exibe o status atual de cada ativo.

---

## Estrutura do projeto

```
industrial-asset-monitor/
├── database.py     # inicializa o banco e cria as tabelas
├── simulator.py    # popula equipamentos e gera leituras de sensores
├── alerts.py       # verifica thresholds e imprime alertas
├── report.py       # exibe status atual de cada equipamento
├── main.py         # ponto de entrada — orquestra todos os módulos
└── README.md
```

---

## Como rodar

**Pré-requisitos:** Python 3.8+. Nenhuma dependência externa — só biblioteca padrão.

```bash
# clone o repositório
git clone https://github.com/seu-usuario/industrial-asset-monitor.git
cd industrial-asset-monitor

# rode o sistema
python main.py
```

Na primeira execução, o banco é criado automaticamente e os equipamentos são cadastrados. Cada execução gera um novo conjunto de leituras.

---

## Thresholds configuráveis

Definidos como constantes em `alerts.py`:

| Sensor | Limite máximo |
|---|---|
| Temperatura | 75.0 °C |
| Pressão | 8.0 bar |
| Vibração | 4.0 Hz |

---

## Exemplo de saída

```
Motor de simulação gerou dados

ALERTA — Compressor de Ar CP-01        | temperatura: 89.11° (máx: 75.00°) | vibração: 4.40 Hz (máx: 4.00 Hz)
ALERTA — Bomba Dosadora BD-03          | pressão: 9.18 bar (máx: 8.00 bar)

Bomba Dosadora BD-03           | 2026-06-24 15:51:40  | ALERTA
Compressor de Ar CP-01         | 2026-06-24 15:51:40  | OK
Misturador Industrial A        | 2026-06-24 15:51:39  | OK
```

---

## Tecnologias

- Python 3.8+
- SQLite3 (nativo)
- `datetime`, `random`, `typing` (biblioteca padrão)

---

## Autor

Gustavo Calvo — Estudante de Engenharia da Computação (FESA) e Inteligência Artificial (Univesp).

---
---

# Industrial Asset Monitor

A Python-based industrial asset monitoring system using SQLite. Simulates sensor readings from factory equipment, detects anomalies through configurable thresholds, and generates real-time status reports.

Developed as part of studies in manufacturing systems and industrial automation.

---

## The problem

In industrial environments, equipment such as compressors, pumps, and mixers run continuously and must be monitored to prevent failures. Without a centralized system, anomalies go unnoticed until they cause a line stoppage.

## The solution

The system collects simulated temperature, pressure, and vibration readings from each asset, stores them in a database, and triggers alerts when any value exceeds its operational limit. A consolidated report displays the current status of each asset.

---

## Project structure

```
industrial-asset-monitor/
├── database.py     # initializes the database and creates tables
├── simulator.py    # registers equipment and generates sensor readings
├── alerts.py       # checks thresholds and prints alerts
├── report.py       # displays current status for each asset
├── main.py         # entry point — orchestrates all modules
└── README.md
```

---

## How to run

**Requirements:** Python 3.8+. No external dependencies — standard library only.

```bash
# clone the repository
git clone https://github.com/your-username/industrial-asset-monitor.git
cd industrial-asset-monitor

# run the system
python main.py
```

On the first run, the database is created automatically and the equipment is registered. Each subsequent run generates a new set of sensor readings.

---

## Configurable thresholds

Defined as constants in `alerts.py`:

| Sensor | Maximum limit |
|---|---|
| Temperature | 75.0 °C |
| Pressure | 8.0 bar |
| Vibration | 4.0 Hz |

---

## Sample output

```
Simulation engine generated data

ALERT — Compressor CP-01        | temperature: 89.11° (max: 75.00°) | vibration: 4.40 Hz (max: 4.00 Hz)
ALERT — Pump BD-03              | pressure: 9.18 bar (max: 8.00 bar)

Pump BD-03                | 2026-06-24 15:51:40  | ALERT
Compressor CP-01          | 2026-06-24 15:51:40  | OK
Industrial Mixer A        | 2026-06-24 15:51:39  | OK
```

---

## Tech stack

- Python 3.8+
- SQLite3 (built-in)
- `datetime`, `random`, `typing` (standard library)

---

## Author

Gustavo Calvo — Computer Engineering student (FESA) and Artificial Intelligence student (Univesp).
