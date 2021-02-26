1. clone
2. checkout
3. update base/package.json change [project_id]/[name] to match you GCP project and desired name
    "cloud:build": "gcloud builds submit --tag gcr.io/[project_id]/[name]",
    "cloud:deploy": "gcloud run deploy --image gcr.io/[project_id]/[name] --platform managed"

4. npm install
5. npm run cloud:build
6. npm run cloud:deploy
6. configure the clould run service for you custom domain.