# Deployment Guide for Iris Classification on Render

This guide explains how to deploy the Iris Classification project on [Render](https://render.com). Render is a cloud platform that provides free and paid plans for hosting web applications, APIs, and static sites.



## Prerequisites

Before deploying, ensure the following:

1. You have a Render account. Sign up [here](https://render.com/signup) if you don’t have one.
2. The project repository is hosted on GitHub (e.g., [PRAVALIKA150/Iris_classification_deployment](https://github.com/PRAVALIKA150/Iris_classification_deployment)).
3. The project includes:
   - `app.py` (Flask application file)
   - `requirements.txt` (Python dependencies)
   - Any required model files (e.g., `iris_model.pkl`).

---

## Steps to Deploy

### Step 1: Create a New Web Service on Render
1. Go to the [Render dashboard](https://dashboard.render.com/).
2. Click **"New"** and select **"Web Service"**.
3. Connect your GitHub account to Render (if you haven’t already) and select your repository.

---

### Step 2: Configure the Web Service
1. In the **"Create a New Web Service"** page, configure the following:

   - **Name:** Enter a name for your application (e.g., `iris-classification`).
   - **Branch:** Select the branch you want to deploy (e.g., `main`).
   - **Build Command:** Leave it as default (`pip install -r requirements.txt`).
   - **Start Command:** Enter:
     ```bash
     python app.py
     ```
   - **Environment:** Select **"Python 3"** as the runtime environment.

2. Leave other options as default or configure based on your project’s needs.

3. Click **Create Web Service**.



### Step 3: Add Environment Variables (If Required)
If your application uses environment variables (e.g., API keys), add them under the **Environment** tab in the Render dashboard.



### Step 4: Wait for the Build
Render will automatically start building and deploying your application. This may take a few minutes. Once the deployment is successful, you’ll see a **Live** status.



### Step 5: Access the Application
1. Copy the URL provided by Render (e.g., `https://iris-classification.onrender.com`).
2. Open the URL in a web browser to access your deployed application.


## Troubleshooting

### Common Issues
1. **Application Error:**
   - Check the Render logs for error details and fix any issues in your code or dependencies.

2. **Dependency Errors:**
   - Ensure all required libraries are listed in `requirements.txt`.

3. **Port Issues:**
   - Ensure your Flask app uses `0.0.0.0` as the host and the `PORT` environment variable for the port:
     ```python
     app.run(host='0.0.0.0', port=int(os.environ.get('PORT', 5000)))
     ```

### Logs
View the application logs in the Render dashboard under the **Logs** tab to debug issues.


## Updating the Deployment
To update the deployed application:
1. Push changes to the connected GitHub repository.
2. Render will automatically detect changes and trigger a new deployment.



## Resources
- [Render Documentation](https://render.com/docs)
- [Flask Deployment Guide](https://flask.palletsprojects.com/en/2.2.x/deploying/)


With this guide, your Iris Classification project should be successfully deployed and accessible on Render. Let me know if you face any challenges!


### Public URL
Your application is now live and can be accessed at https://iris-deployment-vsy3.onrender.com/
