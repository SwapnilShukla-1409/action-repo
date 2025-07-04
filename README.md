# Action Repo

This repository is used to generate GitHub events (Push and Pull Requests) that are sent to a webhook endpoint for processing and display.

## 📌 Purpose

This repo triggers GitHub Webhooks when:
- Code is **pushed** to a branch
- A **Pull Request** is opened or merged

These events are received by the companion repository: [`webhook-repo`](https://github.com/SwapnilShukla-1409/webhook-repo)

## 🧪 How to Use

1. **Clone the Repo**

git clone https://github.com/SwapnilShukla-1409/action-repo.git
cd action-repo
Trigger a Push Event

bash
Copy
Edit
echo "Test update" >> test.txt
git add .
git commit -m "Test push event"
git push origin main
Trigger a Pull Request and Merge Event

Create a new branch

Make changes and push it

Open a PR from the branch to main

Merge it to generate a pull_request and merge event

🔧 Webhook Configuration
In GitHub → Settings → Webhooks:

Payload URL:
https://<your-deployment-domain>/webhook
(e.g. https://webhook-receiver.fly.dev/webhook)

Content Type: application/json

Secret: (use same as in webhook-repo)

Events to Send:

✅ Push events

✅ Pull request events

Click Add Webhook.

🔗 Related Project
webhook-repo: Flask app that receives GitHub Webhook events, stores them in MongoDB, and displays them in a simple web UI.
