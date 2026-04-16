# LLM Jazz Lick App — Roadmap

## Overview

This project builds a phrase-centric jazz improvisation intelligence system over the Jazzomat / Weimar Jazz Database, culminating in an LLM-powered chat application for querying, analyzing, and explaining jazz improvisation.

The core idea is to move from raw symbolic event data → phrase-level musical intelligence → hybrid SQL + embedding retrieval → LLM reasoning interface.

---

## 🧭 System Evolution

This project is built in three phases:

---

# Phase 1 — Research Sandbox (Python + Jupyter)

### Goal

Understand the data, validate musical representations, and extract meaningful phrase-level structure.

### Stack

- Python
- Jupyter notebooks
- SQLite (Jazzomat database)
- MeloSpySuite CLI tools:
    - melconv
    - melfeature
    - melpat
- pandas, numpy
- matplotlib (for validation plots)

### Key Activities

#### 1. Phrase Extraction

- Use `sections` table (PHRASE type)
- Align with `melody` events
- Attach chord context from `beats`

#### 2. Feature Exploration

- Interval sequences
- Rhythmic density
- Chord-tone alignment
- Chromatic behavior

#### 3. Validation via MeloSpySuite

- Use CLI tools as reference feature generators
- Compare against custom implementations

### Deliverables

- Notebook: phrase segmentation pipeline
- Notebook: feature extraction + visualization
- UMAP / clustering sanity checks

---

# Phase 2 — Structured Data Layer (Postgres / Warehouse Thinking)

### Goal

Turn research artifacts into a stable, queryable analytical data model.

### Stack

- Postgres (primary datastore)
- SQLAlchemy (or raw SQL)
- Optional: DuckDB for analytics experimentation
- Optional: dbt for transformation modeling

### Core Data Model

#### Existing Jazzomat Tables

- melody
- beats
- sections
- solo_info
- composition_info
- record_info

#### New Core Abstraction

### phrase_segments (PRIMARY UNIT)

- phrase_id
- melid
- start_event_id
- end_event_id
- start_bar / end_bar
- chord_sequence
- form_context
- chorus_id
- style metadata (joined from solo_info)

### phrase_features

- interval features
- rhythm features
- harmonic behavior metrics

### pattern_matches (optional)

- motif occurrences
- repeated structures

---

### Key Concepts Learned

- Data modeling for analytical systems
- Feature engineering pipelines
- Materialized views vs raw tables
- Warehouse-style thinking applied to music

---

# Phase 3 — LLM Application Layer

### Goal

Build a chat-based interface that allows natural language querying of jazz improvisation.

---

## Architecture

### 1. Query Planner (LLM)

Transforms natural language → structured queries:

- SQL over phrase_segments
- optional vector search

---

### 2. Retrieval Layer

#### A. Structured Retrieval (Primary)

- SQL queries over phrase_features

#### B. Semantic Retrieval (Secondary)

- embeddings (optional)
- pgvector or FAISS

---

### 3. Reasoning Layer (LLM)

- Explains retrieved phrases
- Synthesizes patterns
- Generates musical insights

---

## Stack

- FastAPI backend
- Postgres (+ optional pgvector)
- OpenAI API (or other LLM provider)
- React frontend (future)

---

## Interaction Flow

User Query
→ LLM Query Planner
→ SQL / Vector retrieval
→ Phrase-level results
→ LLM explanation & synthesis

---

# MeloSpySuite Role

MeloSpySuite is used as:

- Offline feature extraction tool
- Validation system
- Pattern discovery aid

NOT part of production runtime.

---

# 🧠 Key System Principle

> Everything revolves around phrase_segments as the atomic unit of musical meaning.

---

# 🚨 Critical Design Rule

Do NOT build LLM or vector systems before:

- phrase segmentation is stable
- chord alignment is correct
- phrase features are meaningful and interpretable

---

# 🧭 Final Outcome

A system that allows:

- Querying jazz improvisation like a database
- Searching by harmonic behavior
- Finding motif similarity across players
- Explaining improvisational structure via LLM

---

# Suggested Learning Outcomes

This project teaches:

- Modern data warehouse design
- Feature engineering pipelines
- Hybrid SQL + vector retrieval systems
- LLM tool-use architectures
- Music information retrieval at scale

---

# End State Vision

A deployed application where a user can ask:

- “Show me bebop enclosures over V7 chords”
- “Compare Parker and Stitt phrasing”
- “Find phrases similar to this lick”
- “Explain what makes this solo sound ‘cool jazz’”

and receive:

- structured musical evidence
- retrieved phrase examples
- LLM-generated musical analysis
