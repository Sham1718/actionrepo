# GitHub Action Repository

This repository is used to generate GitHub events for testing the webhook system.

The purpose of this repository is to trigger events such as **Push**, **Pull Request**, and **Merge** which are then sent to a webhook endpoint implemented in the webhook-repo.

---

## Purpose

This repository triggers GitHub events that are captured by a webhook receiver built using Flask.

The webhook receiver processes the events and stores minimal event data in MongoDB.

---

## Events Used

The following GitHub events are generated from this repository:

- Push
- Pull Request
- Merge

These events are sent automatically to the webhook endpoint configured in the repository settings.

---

## How to Trigger Events

### Push Event

Make any commit and push it to the repository.

Example:

git add .
git commit -m "test push"
git push origin main

This will trigger a **push event**.

---

### Pull Request Event

Create a new branch and push it.

git checkout -b feature-1
git push origin feature-1

Go to GitHub and create a **Pull Request** from `feature-1` to `main`.

This will trigger a **pull_request event**.

---

### Merge Event

Open the created Pull Request and click:

Merge Pull Request

This will trigger the **merge event**.

---

## Webhook Configuration

The webhook is configured in:

Repository → Settings → Webhooks

Payload URL points to the webhook endpoint in the webhook-repo.

The webhook sends events in **JSON format** to the Flask server.

---

## Related Repository

The webhook receiver and UI implementation are available in the following repository:

webhook-repo

This repository captures events and stores them in MongoDB.