# Lyra_Air_Health

## 🧠 Objective
Fine-tuned `gpt-3.5-turbo` model for assessing environmental health risks based on meteorological and atmospheric conditions.

## 📥 Input Data
- Temperature
- Humidity
- Thermal inversion (yes/no)
- Pollen level (low/medium/high)
- AQI (Air Quality Index, 1 to 10)
- Wind > 20 km/h (yes/no)
- Rain > 20 mm (yes/no)

## 🧾 Output
- Allergy risk: low / medium / high / very high / extreme
- Cardiovascular risk: same scale

## 🔍 Performance Test
- 5 typical prompts: same behavior as base model
- 3 edge-case prompts: significant divergence (see table)

| Prompt                    | Cardio Risk (base) | Cardio Risk (fine-tuned) |
|--------------------------|--------------------|---------------------------|
| Stagnant heatwave        | high               | **extreme**               |
| Post-pollen thunderstorm | medium             | **very high**             |
| Invisible winter smog    | very high          | **extreme**               |

## 🧪 Prompt Example
```
Temperature: 32°C
Humidity: 75%
Inversion: yes
Pollen: high
AQI: 9
Wind > 20 km/h: no
Rain > 20 mm: yes
```

## 📁 File Structure
```
Lyra_Air_Health/
├── datasets/
│   ├── dataset_lyra_air_sante.jsonl
│   ├── validation_lyra_air_sante.jsonl
│   └── dataset_lyra_air_sante_verification_visuelle.xls
├── prompts/
│   └── exemples_prompts.txt
├── synthèse_Fr/
│   └── Synthèse Lyra Air santé.pdf
└── README.md
```

## 🛠️ Usage
Compatible with Make, n8n, or any OpenAI API supporting fine-tuned models.

## 📄 License
For educational and demonstrative use only.
