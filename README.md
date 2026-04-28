# ESA Decision Support Render Deployment

[![Deploy to Render](https://render.com/images/deploy-to-render-button.svg)](https://render.com/deploy?repo=https://github.com/xiaominmo/ESA-hyporesponse)

This repository contains the minimum files required to deploy the ESA decision-support prototype to Render.

## Included
- `app.py` - Streamlit UI
- `inference.py` - model inference and phenotype assignment logic
- `best_model_XGBoost.joblib` - trained prediction model
- `cluster_metadata.json` - revised 2026-04-27 K=3 phenotype centroid, scaling, and naming metadata
- `requirements.txt` - Python dependencies
- `render.yaml` - Render Blueprint service definition

## Deploy on Render
1. Click the Deploy to Render button above, or open this URL:
   `https://render.com/deploy?repo=https://github.com/xiaominmo/ESA-hyporesponse`
2. Sign in to Render and connect your GitHub account if prompted.
3. Review the Blueprint settings and approve the deployment.
4. Render will build the service and provide a public `*.onrender.com` URL.

## Manual Web Service Setup
If you create a Web Service manually instead of using the Blueprint:
- Repository: `https://github.com/xiaominmo/ESA-hyporesponse`
- Branch: `main`
- Runtime: Python
- Build command: `pip install -r requirements.txt`
- Start command: `streamlit run app.py --server.port $PORT --server.address 0.0.0.0`
- Environment variable: `PYTHON_VERSION=3.11.9`

## Important note
This deployment bundle intentionally excludes the raw CSV source data. It only contains the files required for online inference.