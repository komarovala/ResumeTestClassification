# ResumeTestClassification

Этот репозиторий содержит эксперименты по классификации текстов резюме на основе датасета [Résumé Atlas](https://huggingface.co/datasets/ahmedheakl/resume-atlas).

## Описание экспериментов

В папке [Notebooks](Notebooks) представлены два основных Colab-ноутбука:

- [`resume_atlas_stack.ipynb`](Notebooks/resume_atlas_stack.ipynb):  
  Полный стек современных моделей для классификации резюме.  
  - Скачивание датасета
  - DAPT-предобучение DeBERTa-v3-Large
  - Обучение 3 seed-моделей + Longformer-Large
  - Ансамблирование моделей  
  Достигается ≈ 94.4 % Top-1 и ≈ 98.9 % Top-5 точности.

- [`resume_atlas_classification_benchmark.ipynb`](Notebooks/resume_atlas_classification_benchmark.ipynb):  
  Сравнительный бенчмарк классических и современных моделей:  
  - TF‑IDF + SVM
  - FastText (Wiki vectors)
  - CareerBERT-base/large
  - RoBERTa-DA  
  В конце выводится таблица с метриками: Top‑k accuracy, F1‑macro, Precision‑macro, Recall‑macro.

  В папке [src](src) представлены основной код для запуска пайлайнов обучения:

## Метрики

Результаты ансамбля моделей сохранены в [`metrics/ensemble_metrics.json`](/metrics/ensemble_metrics.json).

## Требования

- GPU ≥ 24 GB (A100/V100) для запуска полного стека

## Цель

Показать возможности современных NLP-моделей и ансамблей для автоматической классификации резюме, сравнить их с классическими подходами и современными подходами, повысив качество классификации.