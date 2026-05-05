# 🇦🇱 Lajme Shqip - Agregator Lajmesh

Aplikacion web (PWA) që mbledh lajme nga 14 burime shqiptare përmes RSS dhe i shfaq në një vend të vetëm.

## ✨ Funksionalitetet

- 📰 **14 burime lajmesh** (Panorama, Shqiptarja, Express, Blic, ABC News, etj.)
- 🔍 **Kërkim me keyword** (p.sh. "krim", "politikë", "sport")
- 📂 **Filtrim sipas kategorive** (Politikë, Kronikë, Sport, Ekonomi, Botë)
- 🤖 **Përmbledhje me AI** (përmes OpenRouter - falas)
- 🔔 **Badge "I RI"** për lajmet e 24 orëve të fundit
- 📤 **Shpërndarje** e lajmeve
- 📱 **PWA** - mund të shtohet në Home Screen të iPhone/Android
- 🔄 **Përditësim automatik** çdo orë përmes GitHub Actions

## 🚀 Si ta hostosh në GitHub Pages

### 1. Krijo Repository
- Shko në [github.com](https://github.com)
- Krijo repository të ri publik me emrin `lajme-shqip`

### 2. Ngarko File-t
Ngarko këto file në repository:
- `index.html` - Aplikacioni kryesor
- `fetch_news.py` - Script Python për marrjen e lajmeve
- `.github/workflows/update-news.yml` - GitHub Actions workflow
- `news.json` - (do krijohet automatikisht)

### 3. Aktivizo GitHub Actions
- Shko tek **Settings > Actions > General**
- Tek **Workflow permissions**, zgjidh **"Read and write permissions"**
- Kliko **Save**

### 4. Aktivizo GitHub Pages
- Shko tek **Settings > Pages**
- Zgjidh branch **main** dhe folder **/(root)**
- Kliko **Save**

### 5. Nis Workflow-in Manualisht
- Shko tek **Actions** tab
- Kliko **"Update News Feed"**
- Kliko **"Run workflow"**
- Prit 2-3 minuta që të përfundojë

### 6. Hape Aplikacionin
- URL-ja do jetë: `https://USERNAME.github.io/lajme-shqip/`
- Hape në Safari të iPhone → Share → Add to Home Screen

## 🤖 Si ta aktivizosh Përmbledhjen me AI

1. Shko tek [openrouter.ai/keys](https://openrouter.ai/keys)
2. Krijo llogari falas (me Google/GitHub)
3. Kopjo API Key (`sk-or-v1-...`)
4. Hape aplikacionin → ⚙️ Cilësimet → ngjit çelësin → Ruaj

Modelet falas:
- `meta-llama/llama-3.3-70b-instruct:free`
- `deepseek/deepseek-chat:free`
- `google/gemini-2.5-flash-preview:free`

## 🔄 Përditësimi Automatik

GitHub Actions ekzekutohet **çdo orë** automatikisht dhe:
1. Merr lajmet nga të 14 burimet RSS
2. I ruan në `news.json`
3. Commit & push në repository
4. Aplikacioni i lexon nga `news.json` (same-origin, pa CORS!)

## 📁 Struktura e Projektit

```
lajme-shqip/
├── .github/
│   └── workflows/
│       └── update-news.yml    # GitHub Actions - çdo orë
├── index.html                  # Aplikacioni PWA
├── fetch_news.py              # Script Python për RSS
├── news.json                  # Të dhënat (krijohet automatikisht)
└── README.md
```

## ⚠️ Vërejtje

- Disa faqe shqiptare mund të kenë RSS të pafunksionueshëm herë pas here
- Script-i përballon gabimet dhe vazhdon me burimet e tjera
- Nëse `news.json` nuk ekziston, aplikacioni shfaq mode Demo

## 📝 Licenca

Projekt për përdorim personal.
