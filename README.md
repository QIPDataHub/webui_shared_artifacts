# webui_shared_artifacts — Built Web UI bundles (CAR & Collector)

> **Note**  
> - These are artifacts for **JEDx Phase II Pilot**  
> - Not meant for production  
> - Questions can be sent to **Jim Goodell (jimgoodell@qi-partners.com)** and **Alex Jackl (alex@bardicsystems.com)**

---

This repository hosts **zipped `/dist` builds** of the JEDx Web UI applications:
- `dist.zip` — **CAR (Sender) app** build
- `dist_COLLECTOR.zip` — **Collector (Receiver) app** build

## How to deploy to S3 static hosting
1. **Download** the appropriate ZIP and **extract** it locally.  
2. **Upload the *contents* of the extracted `dist` folder** (not the folder itself) to the target S3 bucket:  
   - CAR (Sender): `<your-car-ui-bucket>`  
   - Collector (Receiver): `<your-collector-ui-bucket>`
3. Ensure the bucket (or its CloudFront distribution) is configured for **static website hosting**:  
   - *Index document*: `index.html`  
   - *Error/SPA fallback*: `index.html` (or `404.html` if you use a custom page)  
4. If fronted by **CloudFront**, perform an **invalidation** (e.g., `/*`) after upload.  
5. (Optional) Use **versioned subfolders** or `Cache-Control` headers to manage browser caching.
