# 🚀 Red Hat OpenShift Developer Sandbox Setup Guide

Complete step-by-step guide:  
From **Red Hat account creation → OpenShift Sandbox → Dev Spaces Workspace → VS Code connection**

---

## 📌 Prerequisites

- ✅ Internet connection  
- ✅ VS Code installed  
- ✅ Git installed (optional but recommended)  
- ✅ Basic terminal knowledge  

---

# Step 1: Create a Red Hat Developer Account

Go to:  
👉 https://developers.redhat.com/

1. Click **Log In**
2. Select **Register for a Red Hat account**
3. Fill in:
   - First name  
   - Last name  
   - Email  
   - Password  
   - Country  
4. Verify your email  

✅ Your Red Hat account is ready.

---

#  Step 2: Start OpenShift Developer Sandbox

Go to:  
👉 https://developers.redhat.com/developer-sandbox

1. Click **Start your trial**
2. Log in with your Red Hat account
3. Accept terms & conditions
4. Wait for provisioning (1–5 minutes)

You will be redirected to:  
👉 https://sandbox.redhat.com

---

#  Step 3: Access OpenShift from Sandbox Dashboard

Inside the Developer Sandbox dashboard you will see:

- OpenShift  
- OpenShift AI  
- Dev Spaces  

Click:  
👉 **OpenShift → Try it**

This opens the **OpenShift Web Console**.

---

#  Step 4: Create a Dev Spaces Workspace

Dev Spaces allows you to code in the browser using a cloud IDE.

---

## 🔹 4.1 Open Dev Spaces

From Sandbox dashboard:

<img width="1280" height="582" alt="image" src="https://github.com/user-attachments/assets/476e8569-45f8-4e7e-ab63-6b5c70fffc9c" />

👉 Click **Dev Spaces → Try it**

You will be redirected to:

    https://devspaces.apps.<cluster>.openshiftapps.com

---

## 🔹 4.2 Login to Dev Spaces

1. Click **Log in with OpenShift**
2. Authorize access  

You will see the **Create Workspace** page.
<img width="1280" height="575" alt="image" src="https://github.com/user-attachments/assets/4c827782-77e2-4a6e-9a92-f6b4f35bcb74" />

---

## 🔹 4.3 Create a Workspace (Method 1: Import from Git)

Under **Import from Git**:

1. Paste a Git repository URL  

   Example:

       https://github.com/sclorg/nodejs-ex.git

2. Click **Create & Open**
   <img width="1280" height="581" alt="image" src="https://github.com/user-attachments/assets/c1b7f6ce-66db-440c-8309-ea23d2586a92" />

4. ⏳ Wait for workspace to start
<img width="1280" height="458" alt="image" src="https://github.com/user-attachments/assets/a9c349f7-14cf-413e-89e4-d148e5d4de28" />

---

## 🔹 4.4 Create Workspace (Method 2: Sample Workspace)

1. Scroll to **Select a Sample**
2. Choose a sample (Node.js, Java, etc.)
3. (Optional) Enter workspace name
4. Click **Create & Open**

---

## 🔹 4.5 Workspace Environment

Once created, your workspace includes:

- VS Code-like editor  
- Integrated terminal  
- File explorer  
- OpenShift tools  
- Kubernetes support  

You are now coding inside OpenShift ☁️

---

#  Step 5: Install OpenShift CLI (oc)

---

## 🔹 5.1 Download CLI

In OpenShift Web Console:

1. Click your username (top right)
2. Click **Command Line Tools**
3. Download OpenShift CLI for your OS  

Or directly:

👉 https://mirror.openshift.com/pub/openshift-v4/clients/oc/latest/

---

## 🔹 5.2 Install CLI

### Windows

1. Extract ZIP  
2. Move `oc.exe` to:

       C:\Windows\System32

   OR add to PATH

### macOS / Linux

    tar -xvf openshift-client.tar.gz
    sudo mv oc /usr/local/bin/

---

## 🔹 5.3 Verify Installation

    oc version

---

#  Step 6: Login to OpenShift via CLI
<img width="1280" height="485" alt="image" src="https://github.com/user-attachments/assets/7cbea043-ba4b-4013-9a34-db89a316d4d5" />

In Web Console:
<img width="1280" height="578" alt="image" src="https://github.com/user-attachments/assets/57edaf19-cbef-486c-acf2-bd14ba26373e" />

1. Click your username  
2. Click **Copy login command**
3. Click **Display token**
4. Copy the `oc login` command  

Example:

    oc login --token=sha256~XXXXX --server=https://api.sandbox.xxxx.openshiftapps.com:6443
<img width="1280" height="537" alt="image" src="https://github.com/user-attachments/assets/7d3b4904-b482-4666-a6a8-494c149a79ce" />

Verify:

    oc whoami

---

#  Step 7: Connect OpenShift to VS Code

---

## 🔹 7.1 Install VS Code Extensions

Open VS Code → Extensions → Install:

- ✅ OpenShift Connector  
- ✅ Kubernetes  
- ✅ Red Hat YAML  

---

## 🔹 7.2 Login to Cluster from VS Code

1. Press:

       Ctrl + Shift + P

2. Search: `OpenShift: Login`
3. Select your cluster (if already logged in using oc)  

   OR paste server URL + token manually

---

## 🔹 7.3 Verify Connection

Open **OpenShift Explorer** in VS Code.

You should see:

- Projects  
- Pods  
- Deployments  
- Services  
- Routes  

---

#  Step 8: Create a New Project

    oc new-project my-dev-project

Check:

    oc projects

---

#  Step 9: Deploy Sample Application

    oc new-app nodejs:18~https://github.com/sclorg/nodejs-ex.git

Expose service:

    oc expose svc/nodejs-ex

Get route:

    oc get route

Open the route URL in your browser 🚀

---

# 🟢 Alternative: Use Dev Spaces Terminal Instead of Local CLI

Inside your Dev Space:

1. Click **Terminal → New Terminal**
2. Run:

       oc get pods

No local installation needed.

---

# 🛠 Troubleshooting

**oc not recognized**

- Add `oc` to system PATH.

**Workspace stuck loading**

- Delete workspace and recreate.

**Token expired**

- Re-run `oc login` command.

**VS Code not detecting cluster**

- Restart VS Code.

---

# 🎯 What You Have Successfully Done

✔ Created Red Hat account  
✔ Activated OpenShift Developer Sandbox  
✔ Accessed OpenShift Web Console  
✔ Created Dev Spaces Workspace  
✔ Installed oc CLI  
✔ Connected cluster to VS Code  
✔ Deployed application  

---

# 🏁 Conclusion

You now have a complete cloud-native development workflow:

- 🌐 OpenShift Cluster  
- 💻 Dev Spaces (Cloud IDE)  
- 🖥 Local VS Code Integration  
- ⚙️ CLI Access  
- 🚀 Application Deployment  

Happy Building! 🚀
