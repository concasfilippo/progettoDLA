# progettoNLP
Materiale del progetto per il corso di Natural Language Processing

# Installazion
pip install -r requirements.txt

# Struttura del progetto

Dataset (immagini e testo) non caricato. Presenta la seguente struttura, che si può replicare con lo script pre_processing.ipynb indicato di sotto:
- /pre-processing/datasets/train/[classe]/ #tutte le immagini di classe [classe] per il training
- /pre-processing/datasets/val/[classe]/ #tutte le immagini di classe [classe] per il validation set
- /pre-processing/datasets/test/[classe]/ #tutte le immagini di classe [classe] per il test set
- /pre-processing/datasets/train.json  # json con i dati degli item di train
- /pre-processing/datasets/val.json   # json con i dati degli item di train
- /pre-processing/datasets/test.json   # json con i dati degli item di train

Pre-processing ed analisi del dataset:
- /pre-processing/pre_processing.ipynb 
    Si tratta di uno script per 
    - Trasformare le immagini e le descrizioni in un formato più agevole per lo studio;
    - Analizzare la distribuzione degli item per classe e visualizzarne qualche esempio;
    - Osservare la distribuzione della lunghezza dei testi, sia in formato grezzo sia in base alla tokenizzazione dei modelli pre-trained usati;
    - Extra: visualizzazione delle wordcloud

Modelli usati:

(clip)
- /models/model_clip-vit-large-patch14_GridSearch.ipynb
    Si tratta di uno script con cui è stata eseguita la Grid Search usando come modello clip vit lagre patch 14
- /models/clip-vit-large-patch14_GS.csv sono i risultati della Grid Search
- /models/model_clip_vit_large_patch14_best_analysis.ipynb
    Si tratta dello script con cui è stato analizzato il modello con la configurazione che ha restituito i risultati migliori nella Grid Search, e su cui sono stati fatti i test con le varianti di data Augmentation

(openclip)
- /models/model_openclip_rn50quickgelu_GridSearch.ipynb
    Si tratta di uno script con cui è stata eseguita la Grid Search usando come modello open clip resnet 50 quickgelu ed uno script che non esegue la grid search

- /models/saves_models/ #cartella con alcuni modelli performanti scelti, lanciabili con lo script indicato precedentemente

- /models/model_openclip_rn50quickgelu_best_analysis.ipynb
    Analisi del modello migliore sia da zero che caricando il modello

- /models/model_openclip_rn50quickgelu_best_analysis_DA.ipynb
    Questo script serve per addestarre o caricare i modello con Data Augmentation con open clip rn 50 quickgelu

- /models/model_openclip_rn50quickgelu_kfold_e_confrontoConDA.ipynb
    Baseline per il confronto con la varianete con data augmentation con t-test

- /models/result_analisys.ipynb 
    Script per analizzare le performance dei risultati dei due modelli

(modelli di fusione esplicita degli embeddings)
- /models/model_multimodal_fusion_classifier.ipynb
    Questo script offre la possibilità di provre ogni combinazione di fusione esplicita degli embeddings e classificatore tra
        Tra le strategie di fusione: Concatenazione, Layer di attenzione (Multi Head Attention) e Transformer (quindi cross modale)
        Tra le strategie di classificazione: MLP e Transformer


I file clip-vit-large-patch14_GS.csv e openclip-rn50quickgelu_GS.csv indicano i risultati ottenuti dagli esperimenti con la GridSearch





