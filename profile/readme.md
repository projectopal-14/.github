# Opal 
desktop-приложение для markdown-заметок с AI-функциями.

## Стэк
Frontend:
  Electron + React + TypeScript + Tailwind.
  Целевые платформы desktop: Windows, macOS, Linux.
  Возможно поддержка мобильного приолжения в будущем.

Local core:
  Go binary, поставляется вместе с Electron.
  Отвечает за vault, markdown-файлы, SQLite, индексацию, поиск, embeddings, RAG, AI orchestration.

Storage:
  Markdown-файлы являются источником истины.
  SQLite хранит метаданные, chunks, FTS index, graph links, jobs, AI suggestions, embeddings/vector index.

AI modes:
  1. Fully local:
     пользователь устанавливает Ollama, все AI-запросы выполняются локально.

  2. BYOK:
     пользователь указывает свой API key, локальный Go core напрямую вызывает выбранного AI-провайдера.

  3. Managed cloud:
     пользователь входит в аккаунт, AI-запросы идут через удаленный сервер продукта с лимитами, подпиской и централизованным управлением моделями.

Cloud:
  Опциональный аккаунт нужен для sync, managed AI, billing, device management и backup.

Основные функции:
  CRUD markdown-заметок, просмотр, редактирование, удаление, поиск по тексту, semantic/vector search, graph view, backlinks, AI Q&A по заметкам, AI suggestions через diff/patch, переключение AI-режимов.

## MVP
MVP-1:
  - desktop app: Windows/macOS/Linux
  - локальный Go core
  - open/create vault
  - create/read/update/delete .md
  - folders
  - markdown editor + preview
  - SQLite metadata
  - FTS search
  - basic graph from wikilinks
  - indexing status

MVP-2:
  - chunking
  - embeddings
  - semantic search
  - hybrid search
  - related notes
  - local/BYOK AI mode

MVP-3:
  - RAG chat по заметкам
  - answers with sources
  - AI summary
  - AI tags
  - AI backlinks
  - suggestions/diff

MVP-4:
  - account
  - sync
  - managed cloud AI
  - billing/limits
  - multi-device
