# 🤖 AI Customer Service System

Welcome to my project! This is my first open-source project, built by a 13-year-and-11-month-old developer 🚀.

This repository demonstrates how to build an **automated AI Customer Service System** using Dify, Make, and Google Sheets!

> ⚠️ **Warning**: 
> - **DO NOT** enter any private or sensitive information during testing.
> - This project is a **DEMO / MVP (Minimum Viable Product)** for learning purposes.

---

## 🛠️ Prerequisites

Before getting started, make sure you have accounts on the following platforms:
* [Dify](https://cloud.dify.ai) - AI Workflow Orchestration
* [Make](https://make.com) - Automation Platform
* [Google Sheets](https://docs.google.com) - Database & Data Storage

---

## 🚀 Step-by-Step Guide

### Part 1: Setting up Dify Workflow

1. Log in to your **Dify** account and create a new **Chatflow**.
2. Select **Gemini 2.5 Flash** as your LLM model *(Because I'm poor, so I chose this free/cheap option 😅)*.
3. **System Prompt**: Set strict instructions telling the AI what it *should* and *shouldn't* say.
4. Add an **HTTP Request** node and connect it to the **ANSWER** node.
   * Leave the API URL blank for now (we'll get it from Make later).
   * Change the Request Body from `none` to `JSON`.

---

### Part 2: Building Automation with Make.com & Google Sheets

1. Log in to **Make.com**, create a new scenario, and give it a name.
2. Add and connect the following nodes in order:
   `Webhook` ➡️ `OpenAI` ➡️ `Router` ➡️ `JSON` ➡️ `Google Sheets`
   *(Note: Connect `Gmail` as a separate branch coming out of the `Router`)*.
3. Copy the **Webhook URL** from Make and paste it back into the **HTTP Request API** field in Dify.
4. Configure the **OpenAI** prompt in Make to process incoming messages from Dify and prepare them for Google Sheets.
5. Create a new **Google Sheet** document.
6. In Make.com, set the Webhook trigger to **"Immediately as data arrives"** and save your scenario.

---

### Part 3: Testing & Linking Data

1. Head back to **Dify**, click **Publish**, then click **Preview**.
2. Send a test message to the AI in the chat interface.
3. Go back to the **Google Sheets** node in Make.com. You should now see the data structure! Map the variables output from OpenAI into your Google Sheet rows.
4. Turn on the Make scenario!

---

## 🎉 Done!
You have successfully built an automated AI Customer Service System! Save your work and enjoy building! 🎈
