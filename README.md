# PR Review Bot 
This repository contains an automated GitHub PR review system powered by an LLM.
## Features
* 🤖 Automated pull request reviews
* 🔍 Detects issues like:

  * Missing tests
  * Hardcoded secrets
  * Code quality problems
* 📊 Provides a review score and risk level
* 📝 Posts structured feedback directly on PRs
* ✅ Tracks merge readiness based on:

  * CI status
  * Approvals
  * Change requests

## How It Works

1. A pull request is opened or updated
2. The system fetches changed files and content
3. Large files are summarized using chunking
4. The LLM analyzes the PR
5. A structured review is posted on GitHub

## Setup

1. Create a GitHub App
2. Configure webhook events:

   * pull_request
   * pull_request_review
   * workflow_run
3. Set environment variables:

   * `GITHUB_APP_ID`
   * `GITHUB_PRIVATE_KEY_PEM`
   * `LLM_API_URL`
   * `LLM_API_KEY`
   * `LLM_MODEL`

## Running the System

* Deploy the webhook receiver (e.g., AWS Lambda)
* Connect it to a queue (SQS)
* Process events and store state in a database

## Notes

* Ensure all files end with a newline
* Avoid hardcoding sensitive values
* Keep PRs small for better analysis


