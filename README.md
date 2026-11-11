# Multi-Item Food Detection and Calorie Calculation System (USTH Group Project)

Web-based prototype that detects multiple visible food items from a meal photo (fine-tuned YOLO on a curated VIPER-FoodNet subset) and calculates total meal calories through a human-in-the-loop verification workflow backed by USDA FoodData Central and SQLite.

See [temp1.docx](temp1.docx) for the full 12-week implementation plan.

## Repository Structure

- `data_pipeline/` — VFN dataset audit, cross-split duplicate checks, class filtering, YOLO conversion, and USDA nutrition mapping table (Members 1–2)
- `modeling/` — YOLO training configs, latency benchmarking, confusion/error analysis, and held-out test evaluation scripts (Members 3–4)
- `backend/` — FastAPI service, YOLO inference endpoint, USDA lookup & calorie math, SQLite schema, and unit/API tests (Member 5)
- `frontend/` — React web app (image upload/camera, bounding box overlay editor, portion S/M/L & gram inputs, daily calorie log) (Members 6–7)

## Setup Notes for Teammates

1. **Dataset is NOT in Git** (`vfn_1_0/` is ignored in `.gitignore` because it is ~2.75 GB). Download/extract `vfn_1_0/` into the project root directory before running scripts in `data_pipeline/` or `modeling/`.
2. **Work on your own branch** (e.g., `data-audit`, `cv-yolo`, `backend-api`, `frontend-ui`) instead of pushing directly to `main`.
3. **Always `git pull` before starting work** and check `git status` before committing so large images or `.pt` weights are never committed.
