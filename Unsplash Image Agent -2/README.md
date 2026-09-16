# Unsplash Image Agent -2

**Assignment:** Module 2 — Unsplash Image Agent (n8n)

This project accepts a keyword through a GET Webhook, searches Unsplash, keeps three full-size image URLs, and returns them as JSON.

## Workflow

1. **Webhook** — GET endpoint; accepts a query such as `?q=coffee`.
2. **HTTP Request** — GET `https://api.unsplash.com/search/photos`; sends `query={{$json.query.q}}`, `per_page=3`, and an Unsplash Client-ID header.
3. **Edit Fields** — keeps `images={{$json.results.map(r => r.urls.full)}}`.
4. **Respond to Webhook** — returns the `images` JSON response.

## Expected output

```json
{
  "images": ["url1", "url2", "url3"]
}
```

## Files copied using Drive names

- `Full workflow json file/Unsplash Image Agent (n8n).json`
- `Image-agent apps link/Imageagentappslink.txt`
- `webhook production URL/webhookproductionurl.txt`
- `webhook test URL/webhooktesturl.txt`
- `workflow ss/` — workflow screenshots
- `workflow screenrecod/` — workflow recording
- `image-agent apps screenrecod/` — app recording

## Live/test links from the Drive evidence

- App: `https://image-agent-985258502901.asia-southeast1.run.app`
- Production test: `https://arif9928.app.n8n.cloud/webhook/image-agent?q=cow`
- Webhook test: `https://arif9928.app.n8n.cloud/webhook-test/image-agent?q=tea`

## Evidence

[Open the Module 2 release assets](https://github.com/arifmohiuddin726-ship-it/AI-Email-Assistant-for-a-Dental-Clinic-1/releases/tag/module-2-unsplash-image-agent) to view/download the six workflow screenshots and two screen recordings.

## Security note

The source workflow contained an Unsplash Client-ID. The GitHub copy uses `YOUR_UNSPLASH_ACCESS_KEY` as a safe placeholder. Add the real credential through n8n credentials or a secret manager; do not commit it to a public repository.
