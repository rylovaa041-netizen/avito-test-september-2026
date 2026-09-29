# Как разложить файлы в репозитории

Ноутбук читает `data/train.csv`, `data/test.csv`, `data/events.csv.gz`.
В репозитории сейчас `data` — это файл на 1 байт, а данные лежат в корне. Исправить:

```
git rm data
mkdir data
git mv train.csv test.csv events.csv.gz data/
```

`sample_submission.csv`, `submission.csv`, `metric.py`, `solution.ipynb` остаются в корне.
Если events.csv.gz (12 МБ) не должен попадать в репозиторий, оставьте строку
`data/events.csv.gz` в .gitignore и уберите файл из индекса: `git rm --cached data/events.csv.gz`.
