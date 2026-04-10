# 🛡️ Risk Assessment Dashboard

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![Streamlit](https://img.shields.io/badge/Streamlit-1.32.0+-red.svg)](https://streamlit.io/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

**Una soluzione enterprise-grade per la gestione e valutazione quantitativa dei rischi di progetto, sviluppata con architettura moderna e interfaccia intuitiva.**

## 📋 Indice

- [🎯 Overview](#-overview)
- [✨ Caratteristiche](#-caratteristiche)
- [⚙️ Requisiti di Sistema](#️-requisiti-di-sistema)
- [📦 Installazione](#-installazione)
- [🔧 Configurazione e Utilizzo](#-configurazione-e-utilizzo)
- [🏗️ Architettura](#️-architettura)
- [📊 Metodologia di Valutazione](#-metodologia-di-valutazione)
- [🎨 Personalizzazione](#-personalizzazione)
- [🧪 Testing](#-testing)
- [🚀 Deployment](#-deployment)
- [🐛 Troubleshooting](#-troubleshooting)
- [🤝 Contribuire](#-contribuire)
- [📄 Licenza](#-licenza)

![Heat Map dei Rischi](./screenshots/heat_map_dei_rischi.png)

## 🎯 Overview

Il **Risk Assessment Dashboard** è una soluzione completa per la gestione quantitativa dei rischi aziendali, progettata per team di project management, risk manager e decision maker. La piattaforma integra metodologie standard di risk assessment con un'interfaccia moderna e funzionalità avanzate di reportistica.

### Casi d'Uso Principali

- **Project Risk Management**: Valutazione e monitoraggio rischi di progetto
- **Enterprise Risk Assessment**: Gestione rischi a livello organizzativo  
- **Compliance Management**: Supporto per framework di conformità
- **Strategic Planning**: Analisi dei rischi per decisioni strategiche

## ✨ Caratteristiche

### 📊 Visualizzazione e Analytics
- **Heat Map Interattiva**: Matrice probabilità/impatto con posizionamento preciso per valori decimali
- **Dashboard Real-time**: Monitoraggio KPI e metriche di rischio in tempo reale
- **Grafici Avanzati**: Trend analysis e distribuzione dei rischi per categoria

### 📋 Gestione Dati
- **Tabella Dinamica AgGrid**: CRUD completo con sorting, filtering e grouping
- **Calcolo Automatico**: Priorità e scoring basati su algoritmi configurabili
- **Validazione Dati**: Controlli di integrità e consistenza automatici

### 📄 Reportistica e Export
- **Export Multi-formato**: PDF, Excel, CSV con heat map incorporata
- **Report Personalizzabili**: Template configurabili per diversi stakeholder
- **Scheduling Automatico**: Generazione report programmata

### 💾 Persistenza e Sicurezza
- **Auto-save**: Salvataggio automatico con sincronizzazione real-time
- **Data Backup**: Sistema di backup automatico incrementale
- **Audit Trail**: Log completo delle modifiche e accessi

### 🎨 User Experience
- **Dark/Light Theme**: Interfaccia responsive ottimizzata
- **Performance Optimized**: Gestione efficiente di dataset di grandi dimensioni
- **Accessibility**: Conforme alle linee guida WCAG 2.1

### Funzionalità Demo
- ✅ Visualizzazione rischi in tempo reale
- ✅ Gestione completa CRUD tramite interfaccia intuitiva
- ✅ Export immediato in PDF/Excel
- ✅ Calcolo automatico priorità e scoring

## ⚙️ Requisiti di Sistema

### Software Necessario
- **Python**: versione 3.8 o superiore
- **pip**: gestore pacchetti Python
- **Browser**: Chrome 90+, Firefox 88+, Safari 14+, Edge 90+

### Specifiche Hardware Consigliate
- **RAM**: 4GB (minimo), 8GB (consigliato)
- **Storage**: 500MB spazio libero
- **CPU**: Dual-core 2.0GHz o superiore

## 📦 Installazione

### Installazione Rapida

1. **Clona il repository**
   ```bash
   git clone https://github.com/rstarttt/risk_insight.git
   cd risk_insight
   ```

2. **Crea ambiente virtuale** (altamente raccomandato)
   ```bash
   # Crea ambiente virtuale
   python -m venv venv
   
   # Attivazione su Windows
   venv\Scripts\activate
   
   # Attivazione su macOS/Linux
   source venv/bin/activate
   ```

3. **Installa dipendenze**
   ```bash
   pip install -r requirements.txt
   ```

4. **Verifica installazione**
   ```bash
   streamlit --version
   ```

5. **Avvia l'applicazione**
   ```bash
   streamlit run risk_dashboard.py
   ```

6. **Accedi all'applicazione**
   - Apri il browser su `http://localhost:8501`

### Installazione Docker (Opzionale)

```bash
# Build dell'immagine
docker build -t risk-dashboard .

# Esecuzione del container
docker run -p 8501:8501 risk-dashboard
```

## 🔧 Configurazione e Utilizzo

### Primo Avvio

Al primo avvio, l'applicazione creerà automaticamente:
- File di configurazione `config.yaml`
- Database CSV `risk_data.csv`
- Directory per export `exports/`

### Gestione Rischi

#### Aggiungere un Nuovo Rischio
1. Compila il form **"Aggiungi Nuovo Rischio"**
2. Inserisci **Descrizione** dettagliata del rischio
3. Seleziona **Categoria** dal menu dropdown
4. Imposta **Probabilità** (1-5, incrementi 0.5)
5. Imposta **Impatto** (1-5, incrementi 0.5)
6. La **Priorità** viene calcolata automaticamente (Probabilità × Impatto)
7. Clicca **"Aggiungi Rischio"**

#### Modificare Rischi Esistenti
- Utilizza la tabella interattiva per editing inline
- Doppio-click su cella per modificare valori
- Modifiche salvate automaticamente

#### Eliminare Rischi
- Seleziona checkbox **"Elimina"** nella tabella
- Conferma eliminazione nel popup

### Heat Map Interattiva

La heat map visualizza i rischi secondo il sistema di classificazione standard:

| Priorità | Range Valore | Colore | Descrizione |
|----------|--------------|--------|-------------|
| **Bassa** | 1.0 - 5.0 | 🟢 Verde | Rischi accettabili |
| **Media** | 5.5 - 10.0 | 🟡 Giallo | Rischi da monitorare |
| **Alta** | 10.5 - 15.0 | 🟠 Arancione | Rischi da mitigare |
| **Estrema** | 15.5 - 25.0 | 🔴 Rosso | Rischi critici |

### Export e Reportistica

#### Export PDF
- Report completo con heat map integrata
- Tabella rischi formattata
- Statistiche e metriche riassuntive
- Layout professionale per presentazioni

#### Export Excel
- Fogli multipli: Dati, Statistiche, Grafici
- Formattazione condizionale
- Grafici pivot integrati
- Compatibile con Excel 2016+

## 🏗️ Architettura

```
risk-assessment-dashboard/
├── 📁 src/
│   ├── risk_dashboard.py          # Applicazione principale Streamlit
│   ├── utils/
│   │   ├── data_manager.py        # Gestione persistenza dati
│   │   ├── risk_calculator.py     # Algoritmi calcolo rischio
│   │   └── export_handler.py      # Gestione export PDF/Excel
│   └── components/
│       ├── heatmap.py            # Componente heat map
│       ├── data_table.py         # Tabella interattiva
│       └── forms.py              # Form di input
├── 📁 data/
│   ├── risk_data.csv             # Database principale
│   └── config.yaml               # Configurazioni
├── 📁 exports/                   # Directory export generati
├── 📁 tests/
│   ├── test_risk_calculator.py   # Test unità
│   └── test_data_manager.py
├── 📁 docs/                      # Documentazione
├── requirements.txt              # Dipendenze Python
├── Dockerfile                    # Container Docker
├── .gitignore
└── README.md
```

### Stack Tecnologico

- **Frontend**: Streamlit + AgGrid + Plotly
- **Backend**: Python + Pandas
- **Export**: ReportLab (PDF) + OpenPyXL (Excel)
- **Styling**: CSS Custom + Bootstrap
- **Database**: CSV (opzione upgrade a PostgreSQL/SQLite)

## 📊 Metodologia di Valutazione

### Calcolo del Rischio

Il sistema utilizza la metodologia standard **ISO 31000:2018**:

```python
Valore_Rischio = Probabilità × Impatto
Priorità = funzione(Valore_Rischio)
```

### Scale di Valutazione

#### Probabilità (1-5)
- **1.0**: Molto improbabile (< 5%)
- **2.0**: Improbabile (5-25%)
- **3.0**: Possibile (25-50%)
- **4.0**: Probabile (50-75%)
- **5.0**: Molto probabile (> 75%)

#### Impatto (1-5)
- **1.0**: Trascurabile
- **2.0**: Minore
- **3.0**: Moderato
- **4.0**: Maggiore
- **5.0**: Catastrofico

## 🎨 Personalizzazione

### Modificare Tema Colori

Nel file `src/risk_dashboard.py`, sezione CSS:

```python
# Personalizza colore principale
PRIMARY_COLOR = "#DC143C"  # Crimson Red

# Personalizza gradiente header
HEADER_GRADIENT = "linear-gradient(135deg, #8B0000 0%, #DC143C 50%, #FF6347 100%)"
```

### Configurare Soglie Priorità

Nel file `src/utils/risk_calculator.py`:

```python
def calculate_priority_level(risk_value):
    """Personalizza soglie di priorità"""
    if risk_value >= 16:      # Modifica soglia estrema
        return "Estrema"
    elif risk_value >= 11:    # Modifica soglia alta
        return "Alta"
    elif risk_value >= 6:     # Modifica soglia media
        return "Media"
    else:
        return "Bassa"
```

### Aggiungere Nuove Categorie

Nel file `data/config.yaml`:

```yaml
risk_categories:
  - "Tecnico"
  - "Finanziario"
  - "Operativo"
  - "Strategico"
  - "Compliance"
  - "La Tua Categoria"  # Aggiungi qui
```

## 🧪 Testing

### Eseguire Test

```bash
# Test completi
pytest tests/ -v

# Test con coverage
pytest tests/ --cov=src --cov-report=html

# Test specifici
pytest tests/test_risk_calculator.py -v
```

### Test di Performance

```bash
# Load testing con dati di esempio
python tests/performance_test.py --records=1000
```

## 🚀 Deployment

### Deployment Locale

```bash
# Produzione locale
streamlit run src/risk_dashboard.py --server.port=8501
```

### Deployment Streamlit Cloud

1. Push su GitHub repository
2. Connetti a [Streamlit Cloud](https://streamlit.io/cloud)
3. Deploy automatico da repository

### Deployment Docker

```bash
# Build e deploy
docker build -t risk-dashboard .
docker run -d -p 8501:8501 --name risk-app risk-dashboard
```

### Deployment su Heroku

```bash
# Setup Heroku
heroku create your-risk-dashboard
git push heroku main
```

## 🤝 Contribuire

Accogliamo contributi dalla community! 

### Come Contribuire

1. **Fork** il repository
2. **Crea** branch feature (`git checkout -b feature/amazing-feature`)
3. **Commit** modifiche (`git commit -m 'Add: amazing feature'`)
4. **Push** al branch (`git push origin feature/amazing-feature`)
5. **Apri** Pull Request

### Linee Guida

- Segui PEP 8 per lo stile Python
- Aggiungi test per nuove funzionalità
- Aggiorna documentazione quando necessario
- Usa commit message descrittivi

### Segnalare Bug

Usa [GitHub Issues](https://github.com/lorenzofradeani/risk_insight/issues) con:
- Descrizione dettagliata del problema
- Steps per riprodurre
- Environment (OS, Python version, browser)
- Screenshot se applicabile

## 🐛 Troubleshooting

### Problemi Comuni

#### Errore "Module not found"
```bash
# Reinstalla dipendenze
pip install -r requirements.txt --force-reinstall
```

#### Export PDF non funziona
```bash
# Su Ubuntu/Debian
sudo apt-get install python3-dev build-essential

# Su macOS
brew install cairo pango gdk-pixbuf libffi
```

#### Performance lente con molti dati
- Abilita caching in `config.yaml`
- Considera upgrade a database PostgreSQL
- Ottimizza filtri tabella

### Log e Debug

```bash
# Abilita debug mode
streamlit run risk_dashboard.py --logger.level=debug
```

## 📄 Licenza

Questo progetto è distribuito sotto **Licenza MIT**. Vedi file [LICENSE](LICENSE) per dettagli completi.

```
MIT License - Copyright (c) 2025 rstarttt

Permission is hereby granted, free of charge, to any person obtaining a copy...
```

## 👨‍💻 Autore e Crediti

**Lorenzo Fradeani**
- 🌐 Website: [lorenzofradeani.com](https://lorenzofradeani.com)
- 📧 Email: contact@lorenzofradeani.com
- 🐙 GitHub: [@lorenzofradeani](https://github.com/lorenzofradeani)

<div align="center">

**⭐ Se questo progetto ti è stato utile, lascia una stella su GitHub! ⭐**

---

**Risk Assessment Dashboard** • Gestione Professionale dei Rischi di Progetto  
*Developed with ❤️ by [Lorenzo Fradeani](https://lorenzofradeani.com)*

</div>
