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

## 📁 Project Structure (with comments)
```
Lyra_Air_Health/
├── datasets/                             # 📊 Training and validation data
│   ├── lyra_air_sante_train.jsonl         # JSONL file for fine-tuning the model
│   ├── lyra_air_sante_valid.jsonl      # Validation set to test model generalization
│   └── dataset_lyra_air_sante_verification_visuelle.xls  # Human-readable version of the dataset (Excel)
│
├── prompts/                              # ✍️ Prompt examples used to evaluate the model
│   └── exemples_prompts.txt                  # Includes both standard and edge-case scenarios
│
├── synthèse_Fr/                          # 🗂️ Project summary (in French)
│   └── Synthèse Lyra Air santé.pdf           # Technical and pedagogical documentation (FR)
│
└── README.md                             # 📄 This file – project overview, structure and usage
```

## 🛠️ Usage
Compatible with Make, n8n, or any OpenAI API supporting fine-tuned models.

## 📄 License
For educational and demonstrative use only.
