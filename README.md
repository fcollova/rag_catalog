# RAG Techniques Taxonomy

**Autore: [Francesco Collovà](https://www.linkedin.com/in/fcollova/) · francesco.collova@gmail.com**

Uno strumento interattivo per navigare, classificare e confrontare 40 tecniche di Retrieval-Augmented Generation, basato sul catalogo originale *RAG Techniques Catalog v2.0* (2025).

---

## Contenuto del repository

```
rag-taxonomy.html   →  applicazione interattiva (singolo file, zero dipendenze)
RAG.pdf             →  catalogo originale con le 40 schede tecniche
README.md           →  questo file
```

---

## Demo

> Apri `rag-taxonomy.html` in un browser, oppure pubblica su GitHub Pages e visita:
> `https://<username>.github.io/<repo>/`

---

## Le 5 tassonomie

### 1 · Per assi tecnici
Ogni tecnica classificata lungo 4 dimensioni ortogonali:

| Asse | Domanda |
|------|---------|
| **Dove agisce** | In quale slot della pipeline interviene? (index-time, query-time, retrieval, post-retrieval, generazione) |
| **Complessità** | Quanto tempo e infrastruttura richiede? (★ giorni · ★★ settimane · ★★★ mesi) |
| **Cosa migliora** | Recall, Precision, Faithfulness o Copertura? |
| **Tipo di corpus** | Testo libero, dati strutturati, multimodale o knowledge graph? |

### 2 · Per use case
8 profili di sistema con le tecniche consigliate per ciascuno, suddivise per priorità:

| Use case | Problema centrale |
|----------|-------------------|
| Q&A su knowledge base | Precision, citazioni verificabili |
| Legale / Medicale / Finance | Zero allucinazioni, audit trail |
| Enterprise multi-tenant | Routing, ACL, fonti eterogenee |
| Codebase / Tech docs | Match esatto su terminologia tecnica |
| Ricerca scientifica | Copertura tematica + dettaglio specifico |
| Corpus multimodale | Immagini e diagrammi indicizzabili |
| Assistente conversazionale | Recall su phrasing colloquiale, bassa latenza |
| Knowledge graph / KB relazionale | Query multi-hop su relazioni tra entità |

### 3 · Flowchart decisionale
Un albero di domande binarie che parte dal **sintomo** del sistema (non trova documenti, risposta allucinata, troppo costoso...) e arriva a una shortlist di 3–4 tecniche con spiegazione del perché. È l'unica tassonomia prescrittiva del catalogo — risponde alla domanda "quale tecnica devo usare adesso?"

### 4 · Compatibilità e composizione
Le tecniche non si usano mai da sole. Questa tassonomia mostra:

- **Sinergie** — coppie che si potenziano a vicenda (es. Fusion Retrieval + Reranking)
- **Ridondanze** — coppie che coprono lo stesso slot (es. Contextual Compression vs Relevant Segment Extraction)
- **Conflitti** — coppie che non si devono usare insieme (es. Contextual Compression + Context Window Enhancement)
- **Universali** — tecniche ortogonali a tutta la pipeline (DeepEval, Explainable Retrieval, Multi-faceted Filtering)

### 5 · Profilo di costo
Tabella ordinabile e filtrabile con 3 componenti di costo per ogni tecnica:

| Componente | Descrizione |
|------------|-------------|
| **Index-time** | LLM call o embedding pagati una tantum a indicizzazione |
| **Query-time** | LLM call o retrieval extra per ogni richiesta utente |
| **Infrastruttura** | Modelli aggiuntivi, indici, storage, manutenzione continua |

---

## Le 40 tecniche

Ogni tecnica nel tool ha un badge cliccabile **`#N p.X`** che apre direttamente la pagina corrispondente nel PDF originale.

| # | Tecnica | Categoria |
|---|---------|-----------|
| 1 | Basic RAG | Foundational |
| 2 | Reliable RAG | Foundational |
| 3 | Optimizing Chunk Sizes | Foundational |
| 4 | Proposition Chunking | Foundational |
| 5 | Document Augmentation | Foundational |
| 6 | RAG with CSV / Structured Data | Foundational |
| 7 | Query Transformations | Query Enhancement |
| 8 | HyDE | Query Enhancement |
| 9 | HyPE | Query Enhancement |
| 10 | Step-Back Prompting | Query Enhancement |
| 11 | Multi-Query Retrieval | Query Enhancement |
| 12 | Query Routing | Query Enhancement |
| 13 | Contextual Chunk Headers | Context Enrichment |
| 14 | Semantic Chunking | Context Enrichment |
| 15 | Context Window Enhancement | Context Enrichment |
| 16 | Relevant Segment Extraction | Context Enrichment |
| 17 | Contextual Compression | Context Enrichment |
| 18 | Document Hierarchy (Parent-Child) | Context Enrichment |
| 19 | Late Chunking | Context Enrichment |
| 20 | Fusion Retrieval | Advanced Retrieval |
| 21 | Reranking | Advanced Retrieval |
| 22 | Multi-faceted Filtering | Advanced Retrieval |
| 23 | Hierarchical Indices | Advanced Retrieval |
| 24 | Ensemble Retrieval | Advanced Retrieval |
| 25 | Dartboard Retrieval (MMR) | Advanced Retrieval |
| 26 | Multi-modal RAG | Advanced Retrieval |
| 27 | ColBERT / Token-level Retrieval | Advanced Retrieval |
| 28 | Iterative Retrieval | Iterative |
| 29 | Adaptive Retrieval | Iterative |
| 30 | Retrieval with Feedback Loop | Iterative |
| 31 | FLARE | Iterative |
| 32 | Agentic RAG | Advanced Architecture |
| 33 | Self-RAG | Advanced Architecture |
| 34 | Corrective RAG (CRAG) | Advanced Architecture |
| 35 | Graph RAG | Advanced Architecture |
| 36 | Microsoft GraphRAG | Advanced Architecture |
| 37 | RAPTOR | Advanced Architecture |
| 38 | Sophisticated Controllable Agent | Advanced Architecture |
| 39 | DeepEval | Evaluation |
| 40 | Explainable Retrieval | Explainability |

---

## Come pubblicare su GitHub Pages

**1. Crea il repository**
```bash
git init rag-taxonomy
cd rag-taxonomy
cp /path/to/rag-taxonomy.html index.html
cp /path/to/RAG.pdf RAG.pdf
git add .
git commit -m "Initial commit"
gh repo create rag-taxonomy --public --push
```

**2. Attiva GitHub Pages**

Vai in `Settings → Pages → Branch: main → Folder: / (root)` e salva. Il sito sarà disponibile in ~60 secondi su:
```
https://<username>.github.io/rag-taxonomy/
```

**3. Collega il PDF**

Nel file `index.html`, modifica la variabile in cima allo script:
```js
const PDF_URL = "https://<username>.github.io/rag-taxonomy/RAG.pdf";
```

I badge `#N p.X` apriranno il PDF direttamente alla pagina della scheda.

---

## Come pubblicare su GitHub Gist

Se preferisci un Gist (senza GitHub Pages):

1. Vai su [gist.github.com](https://gist.github.com)
2. Crea un Gist pubblico con il file `rag-taxonomy.html`
3. Per visualizzarlo renderizzato usa:
   ```
   https://htmlpreview.github.io/?https://gist.github.com/<username>/<gist-id>/raw/rag-taxonomy.html
   ```
4. Per collegare il PDF, caricalo su Google Drive con accesso pubblico e usa:
   ```js
   const PDF_URL = "https://drive.google.com/uc?export=download&id=<FILE_ID>";
   ```

---

## Caratteristiche tecniche

- **Zero dipendenze** — nessun framework JS, nessun bundler. Font da Google Fonts, tutto il resto inline.
- **Single file** — `rag-taxonomy.html` è autocontenuto (~97 KB). Si apre direttamente dal filesystem locale.
- **Dark mode** — tema scuro fisso, leggibile su qualsiasi schermo.
- **Responsive** — navigabile su mobile (layout a colonna singola sotto 768px).
- **Accessibile** — navigazione da tastiera, `Escape` chiude la modale PDF.
- **Collega al PDF originale** — ogni tecnica ha un badge che apre la scheda corrispondente nel PDF. Basta impostare `PDF_URL`.

---

## Struttura del codice

```
rag-taxonomy.html
├── <style>              CSS inline (~300 righe, variabili CSS per dark mode)
├── PDF modal            Modale per visualizzare le schede PDF
├── <header>             Titolo, descrizione, link autore, download PDF
├── .nav-tabs            5 tab di navigazione
├── #tab-axes            Tassonomia per assi (left panel + right panel)
├── #tab-uc              Tassonomia per use case
├── #tab-flow            Flowchart decisionale
├── #tab-compat          Tassonomia compatibilità
├── #tab-cost            Profilo di costo (tabella ordinabile)
├── <footer>             Crediti autore, link LinkedIn/GitHub, download PDF
└── <script>             ~700 righe JS vanilla (dati + render functions)
    ├── PDF_URL config
    ├── TECH_MAP (40 tecniche → {num, page})
    ├── TECH_DESC (descrizioni per ogni tecnica)
    ├── AXES data (4 assi × N categorie × M tecniche)
    ├── USE_CASES data (8 use case × cards)
    ├── FLOW_TREE data (albero decisionale)
    ├── COMPAT_DATA (sinergie, ridondanze, conflitti)
    ├── COST_DATA (40 righe × 3 componenti)
    └── render functions + event handlers
```

---

## Catalogo originale

Le 40 schede tecniche sono tratte da:

> **RAG Techniques Catalog** · Versione 2.0 · 2025  
> Francesco Collovà — [francesco.collova@gmail.com](mailto:francesco.collova@gmail.com)  
> [linkedin.com/in/fcollova](https://www.linkedin.com/in/fcollova/)  
>
> Ogni scheda include: descrizione estesa · diagramma architetturale · pro/contro · complessità · esempio di codice Python · riferimenti bibliografici.

Le tassonomie, il flowchart decisionale, la matrice di compatibilità e il profilo di costo sono elaborazioni originali costruite a partire dal catalogo.

---

## Licenza

Il catalogo PDF originale è di Francesco Collovà. Le tassonomie interattive sono rilasciate liberamente — citare l'autore se riutilizzate.
