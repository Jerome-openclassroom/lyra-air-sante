# Lyra_air_santé

## 🧠 Objectif
Modèle fine-tuné sur `gpt-3.5-turbo` pour l’évaluation des risques sanitaires environnementaux à partir de conditions météorologiques et atmosphériques.

## 📥 Données en entrée
- Température
- Humidité
- Inversion thermique (oui/non)
- Pollens (faible/moyen/élevé)
- IQA (Indice de Qualité de l’Air, 1 à 10)
- Vent > 20 km/h (oui/non)
- Pluie > 20 mm (oui/non)

## 🧾 Sortie
- Risques allergique : faible / moyen / élevé / très élevé / extrême
- Risques cardiovasculaire : idem

## 🔍 Tests de performance
5 prompts typiques : comportement identique au modèle de base  
3 prompts extrêmes : différences nettes observées (voir tableau ci-dessous)

| Prompt                      | Risque Cardio (base) | Risque Cardio (fine-tuné) |
|----------------------------|----------------------|----------------------------|
| Canicule stagnante         | élevé                | **extrême**                |
| Orage post-pollinisation   | moyen                | **très élevé**             |
| Smog hivernal invisible    | très élevé           | **extrême**                |

## 🧪 Exemple de prompt
```
Température : 32°C
Humidité : 75%
Inversion : oui
Pollens : élevé
IQA : 9
Vent > 20 km/h : non
Pluie > 20 mm : oui
```

## 📁 Fichiers inclus
- `dataset_lyra_air_sante.jsonl` — 100 cas d'entraînement
- `validation_lyra_air_sante.jsonl` — 30 cas de validation
- `exemples_prompts.txt` — prompts tests typiques et extrêmes

## 🛠️ Usage
Utilisable dans Make, n8n, ou via API OpenAI (fine-tuned model ID requis)

## 📄 Licence
Démonstration pédagogique uniquement.
