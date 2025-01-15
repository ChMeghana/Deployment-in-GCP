# Steps to Deploy a Flutter App and Connect it to a Domain

## Requirements
- **Domain Account**
- **Flutter App**

---

## Step 1: Create a Cloud DNS (Hosted) Zone
1. **Navigate to Cloud DNS**  
   - Open your Google Cloud Platform (GCP) Console and search for **Cloud DNS**.

2. **Create a Public Zone**  
   - Zone Type: **Public**  
   - Zone Name: Choose a unique identifier (e.g., `aquilacode-zone`).  
   - DNS Name: Enter the exact name of the purchased domain (e.g., `aquilacode.com`).  
   - Click **Create** to create the DNS zone.

3. **Add Record Sets**  
   - Click **Add Standard Record Sets** in the DNS zone.  
   - Configure a **CNAME record**:  
     - **DNS Name**: Enter the subdomain (e.g., `www`).  
     - **Resource Record Type**: Select `CNAME`.  
     - **Canonical Name**: Enter `c.storage.googleapis.com`.  
     - Click **Create**.  
   - Ensure the CNAME record is created before setting up the Cloud Storage bucket.

4. **Update Nameservers**  
   - An **NS (Name Server)** record will be created automatically in the zone.  
   - Copy the four nameservers from the record.  
   - Navigate to your domain registrar's **DNS settings**.  
   - Select **Change Nameservers** and use the option for custom nameservers.  
   - Paste the four nameservers copied from GCP.  
   - Complete the verification process, if required.

---

## Step 2: Verify the Domain
1. **Create a TXT Record for Domain Verification**  
   - Open the GCP **Cloud DNS** page and select your DNS zone.  
   - Click **Add Standard Record Set**.  
   - Configure a **TXT record**:  
     - **Resource Record Type**: TXT  
     - Leave the **DNS Name** field empty.  
     - Paste the TXT record value provided in the verification popup.  
     - Click **Create**.

2. **Verify Domain Ownership**  
   - Open the **Google Search Console** using the verification link in the GCP documentation.  
   - Enter the domain name (e.g., `aquilacode.com`) and click **Continue**.  
   - Click **Verify** to confirm ownership.

---

## Step 3: Create a Cloud Storage Bucket
1. **Navigate to Cloud Storage**  
   - Search for **Cloud Storage** in the GCP Console and click **Create Bucket**.

2. **Bucket Configuration**  
   - **Bucket Name**: Use your domain name (e.g., `www.aquilacode.com`).  
   - **Region**: Choose the appropriate location type.  
   - **Storage Class**: Standard.  
   - **Access**: Enable public access.  
   - Click **Create**.

3. **Upload Flutter Web Files**  
   - Drag and drop the built web files (`index.html`, etc.) from your local machine into the bucket.

4. **Set Permissions**  
   - Navigate to the bucket’s **Permissions** tab.  
   - Add a new role:  
     - **Principals**: `allUsers`  
     - **Role**: `Cloud Storage Object Viewer`  
   - Save the changes to allow public access.

5. **Configure Website Settings**  
   - In the bucket listing, click on the triple-dot menu next to the bucket name.  
   - Select **Edit Website Configuration**.  
   - Set:  
     - **Index Page**: `index.html`  
     - Leave the **404 Page** field empty (or specify if needed).  
   - Click **Save**.

---

## Step 4: Deploy and Test the App
1. Open your browser and navigate to your domain name (e.g., `www.aquilacode.com`).
2. Your Flutter app should now be live and accessible through the domain.

---

## Notes
- Ensure the **CNAME record** is set up before creating the bucket.
- Verify that all domain-related changes (e.g., nameservers) have propagated, which may take a few minutes to several hours.
- Keep a backup of your Flutter web files for easy re-deployment if needed.
