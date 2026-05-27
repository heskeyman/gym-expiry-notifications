

# ⏰Gym Subscription Expiry Notifications

An automated workflow that monitors member subscriptions in Airtable and sends timely notifications for upcoming expiries or expired accounts.
## 📸
https://github.com/heskeyman/gym-expiry-notifications/blob/main/002workflow_preview.png?raw=true

## 📂 Project Structure
This repository contains the n8n workflow for:
- **7-Day Warning**: Alerts members expiring within a week.
- **30-Day Reminder**: Early renewal reminder for members expiring in a month.
- **Expired Handling**: Identifies members with past-due dates, updates their status to 'expired' in Airtable, and sends a notification.
- **Admin Reporting**: Sends summary counts to gym management.

## 🛠️ Tech Stack
- **Automation:** n8n
- **Database:** Airtable (Members Table)
- **Email:** Gmail / SMTP Node
- **Logic:** JavaScript Code Node (Date calculation & counting)

## 🚀 Workflow Logic

### Trigger
- Runs on a schedule (e.g., every 6 hours or daily).

### Process
1. **Calculate Thresholds:** Determines dates for `today`, `+7 days`, and `+30 days`.
2. **Parallel Search:** Queries Airtable simultaneously for users in each category.
3. **Action:**
   - Sends personalized HTML emails via Gmail.
   - Updates Airtable records (e.g., changing Status to `expired`).
4. **Reporting:**
   - Uses Code nodes to count successful emails sent per branch.
   - Sends a consolidated or individual summary report to the Gym Admin.

## 📡 How to Import to n8n
1. Open your n8n dashboard.
2. Go to **Workflows** -> **Add Workflow**.
3. Open the **Menu (⋮)** -> **Import from File**.
4. Select `expiry-notifications.json`.
5. Configure your **Airtable** and **Gmail** credentials.
6. Set your workflow variables (`airtable_base_id`, `gym_management_email`).
7. Activate the workflow!


