# n8n QR Code Generator

This n8n workflow generates a QR code from a given URL and outputs the QR code as an image. It's useful for automating the creation of QR codes based on incoming webhooks, forms, or other triggers.

## 🚀 Features

- Accepts a URL via webhook or manual input
- Generates a QR code image using n8n's built-in nodes
- Returns the image as a response or stores it (optional)
- Can be integrated into automation pipelines

## 🛠️ How It Works

1. **Trigger**  
   Use a **Webhook** or **Form Trigger** node to start the workflow.

2. **URL Input**  
   Extract the URL from the incoming data (e.g., `{{$json["url"]}}`).

3. **QR Code Generation**  
   Use the **HTTP Request** or a **Custom Function** node to call a QR generation API or use a JavaScript function to generate the base64 image.

4. **Output**  
   - Return the QR code as an image
   - Optionally store in a file system, Google Drive, or cloud storage

## 📦 Sample Nodes Overview

```yaml
- Webhook (POST)  
- Set (to extract `url`)  
- HTTP Request (to generate QR code from API like `https://api.qrserver.com/v1/create-qr-code/?data=...`)  
- Binary Data (convert to image if needed)  
- Respond with Image (optional)

🔧 Setup Instructions
Clone this repo or import the workflow in your n8n instance.

Replace any sample API keys or endpoints if needed.

Activate the workflow.

Trigger it via the provided webhook URL.

📸 Output
You will receive a PNG image of the QR code generated from your provided URL.

📁 Optional Enhancements
Save images to cloud storage (e.g., Google Drive, Dropbox)

Log URL requests in a database

Add a timestamp or label to the QR code

Schedule QR code generation based on cron triggers

📜 License
This project is open-source and available under the MIT License.

