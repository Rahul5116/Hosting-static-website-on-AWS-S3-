# ☕ Hosting a Static Website for Your Café Using Amazon S3

Welcome! This guide will walk you through hosting your café's static website using **Amazon S3**. Follow these simple steps to get your site live! 🚀

---

## 📌 Task 1: Extracting the Required Files
1. **Download** the `.zip` file containing the website files.
2. **Extract** the `.zip` file to your computer.
3. **Modify** the `index.html` file:
   - Replace the default café name with your own.

---

## 🌍 Task 2: Creating an S3 Bucket for Hosting
1. Open the **AWS Management Console**.
2. Navigate to **Amazon S3**.
3. Click **Create bucket** and set:
   - **Bucket Name**: Choose a unique name.
   - **Region**: Select `US East (N. Virginia) (us-east-1)`.
4. Under **Block Public Access settings**:
   - Uncheck `Block all public access` and acknowledge the warning.
   - Enable **ACLs (Access Control Lists)**.
5. Under **Properties**, scroll down to **Static website hosting**:
   - Enable **Static website hosting**.
   - Set **Index document** to `index.html`.
6. **Save** the settings.

---

## 📂 Task 3: Uploading Content to the S3 Bucket
1. Open your **newly created S3 bucket**.
2. Click **Upload** and add:
   - `index.html` (modified with your café name).
   - The `images` folder.
   - The `CSS` folder.
3. Click **Upload** to complete the process.

---

## 🔓 Task 4: Creating a Bucket Policy for Public Read Access
1. Go to your **S3 bucket**, select the **Permissions** tab.
2. Under **Bucket Policy**, click **Edit** and paste the following policy:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadGetObject",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::your-bucket-name/*"
    }
  ]
}
```
3. **Replace** `your-bucket-name` with your actual bucket name.
4. Click **Save changes**.

---

## 🚀 Task 5: Final Steps
🎉 Your static website should now be **live**!
- To access it, go to the **Properties** tab in your S3 bucket.
- Copy the **Bucket Website Endpoint** and open it in your browser.

Enjoy hosting your café’s website with **Amazon S3!** ☕🌐

