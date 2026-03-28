# RAG Techniques Taxonomy

**Autore: [Francesco Collovà](https://www.linkedin.com/in/fcollova/) · francesco.collova @ gmail.com**

Uno strumento interattivo per navigare, classificare e confrontare 40 tecniche di Retrieval-Augmented Generation, basato sul catalogo originale *RAG Techniques Catalog v2.0* (2025).

---

## Contenuto del repository

```
rag-taxonomy.html   →  applicazione interattiva (singolo file, zero dipendenze)
rag_catalog_v0.1.pdf             →  catalogo originale con le 40 schede tecniche
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

## Catalogo originale

Le 40 schede tecniche sono tratte da:

> **RAG Techniques Catalog** · Versione 2.0 · 2025  
> Francesco Collovà — [francesco.collova @ gmail.com](mailto:francesco.collova @ gmail.com)  
> [linkedin.com/in/fcollova](https://www.linkedin.com/in/fcollova/)  
>
> Ogni scheda include: descrizione estesa · diagramma architetturale · pro/contro · complessità · esempio di codice Python · riferimenti bibliografici.

Le tassonomie, il flowchart decisionale, la matrice di compatibilità e il profilo di costo sono elaborazioni originali costruite a partire dal catalogo.

---

## Licenza

Il catalogo PDF originale è di Francesco Collovà. Le tassonomie interattive sono rilasciate liberamente — citare l'autore se riutilizzate.
