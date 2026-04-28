# Render deployment bundle for ESA decision support

This bundle contains the minimum files required to deploy the local ESA decision-support prototype to Render.

## Included
- `webapp/app.py` — Streamlit UI
- `webapp/inference.py` — model + revised phenotype inference logic
- `clinical_prediction/best_model_*.joblib` — trained prediction model
- `phenotype_clustering/cluster_metadata.json` — revised 2026-04-27 K=3 phenotype centroid, scaling, and naming metadata
- `requirements.txt` — Python dependencies
- `render.yaml` — Render service definition

## Deploy on Render
1. Create a GitHub repository.
2. Upload the full contents of this `render_deploy/` directory to the repository root.
3. In Render, create a new Blueprint or Web Service from that repository.
4. If using Blueprint, Render will read `render.yaml` automatically.
5. If using manual Web Service setup:
   - Build command: `pip install -r requirements.txt`
   - Start command: `streamlit run webapp/app.py --server.port $PORT --server.address 0.0.0.0`
6. After deploy, open the generated Render URL.

## Important note
This deployment bundle intentionally excludes the raw CSV source data. It only contains the files required for online inference.
