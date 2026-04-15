# ZooPredict

Predicting zoonotic disease outbreak risk levels (Low / Medium / High) across Sub-Saharan Africa using machine learning on wildlife surveillance, climate, ecological, and socioeconomic data.

Built as a capstone project combining my BSc Zoology background (OAU) with ML engineering skills.

**Author:** Karimat Opeyemi Abolarinwa — AI/ML Engineer | Nupat Technologies

---

## What it does

Takes monthly country-level features (temperature, rainfall, deforestation, wildlife trade, healthcare capacity, etc.) and classifies outbreak risk into Low / Medium / High. Designed to help surveillance teams prioritise where to deploy limited field resources.

**Diseases covered:** Ebola, Lassa Fever, Monkeypox, Avian Influenza, Rift Valley Fever, Nipah, Marburg, Rabies, Plague, West Nile Fever

## Dataset

2,000 synthetic surveillance records modelled after WHO/PREDICT data structure. 18 raw features + 4 engineered interaction features. Synthetic because WHO case-level microdata isn't publicly available, but the dataset is designed as a drop-in replacement for real data.

## Results

| Model | Test Accuracy | CV Mean |
|---|---|---|
| Logistic Regression | 0.6833 | 0.6614 |
| Random Forest | 0.7333 | 0.7086 |
| Gradient Boosting | 0.7367 | 0.7379 |
| XGBoost | 0.6933 | 0.7357 |

Gradient Boosting and XGBoost perform best on cross-validation. The notebook includes confusion matrices, feature importance analysis, and a policy intervention simulation.

## Key findings

- Surveillance deficit (low coverage + weak healthcare) is the most dangerous risk combination
- Deforestation x population density is a top-5 predictor, supporting the habitat-disruption spillover hypothesis
- Bat and Primate hosts show highest risk rates, consistent with Ebola/Marburg/Nipah reservoir ecology
- Combined interventions reduce outbreak probability far more than any single policy change
- Seasonal risk peaks during the wet season (April-October)

## How to run

**Google Colab:** Upload `ZooPredict_Karimat_Abolarinwa.ipynb` to [Colab](https://colab.research.google.com) and run all cells.

**Locally:**
```bash
git clone https://github.com/Kmart002/ZooPredict.git
cd ZooPredict
pip install -r requirements.txt
jupyter notebook ZooPredict_Karimat_Abolarinwa.ipynb
```

## References

1. Olival et al. (2017). Host and viral traits predict zoonotic spillover. *Nature*, 546, 646-650.
2. Jones et al. (2008). Global trends in emerging infectious diseases. *Nature*, 451, 990-993.
3. Keesing et al. (2010). Biodiversity and infectious disease emergence. *Nature*, 468, 647-652.
4. Mordecai et al. (2019). Thermal biology of mosquito-borne disease. *Ecology Letters*, 22, 1690-1708.
5. Murray et al. (2015). Zoonoses of highest concern in Sub-Saharan Africa. *PLOS NTD*, 9(8).

## License

MIT
