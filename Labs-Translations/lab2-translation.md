#Google Cloud Fundamentals: Getting Started with App Engine

####Sign in to the Google Cloud Platform (GCP) Console
Use the provided credentials.

####Task 1: Initialize App Engine
1. Initialize your App Engine app with your project:

    `gcloud app create --project=$DEVSHELL_PROJECT_ID`

2. Clone the source code repository for a sample application in the hello_world directory:

    `git clone https://github.com/GoogleCloudPlatform/python-docs-samples`
    
3. Navigate to the source directory:
   
    `cd python-docs-samples/appengine/standard_python3/hello_world`
    
####Task 2: Run Hello World application locally
1. Execute the following command to download and update the packages list.
   
    `sudo apt-get update`
    
2. Set up a virtual environment in which you will run your application. Python virtual environments are used to isolate package installations from the system.

    `sudo apt-get install virtualenv`
    
3. Activate the virtual environment.
   
    `source venv/bin/activate`
    
4. Navigate to your project directory and install dependencies.
   
    `pip install  -r requirements.txt`
    
5. Run the application:

    `python main.py`
    
6. In Cloud Shell, click Web preview (Web Preview) > Preview on port 8080 to preview the application.
    
    You should see the application running locally on your browser and printing Hello World. 

####Task 3: Deploy and run Hello World on App Engine
1. Navigate to the source directory:
    
    `cd ~/python-docs-samples/appengine/standard_python3/hello_world`
    
2. Deploy your Hello World application.
   
    `gcloud app deploy`
    
3. Get the application URL:

    `gcloud app browse`
    
    Copy and paste the URL into a new browser window.
    
    Now you have your application deployed and running on the web.
    
####Task 4: Disable the application
App Engine offers no option to Undeploy an application. After an application is deployed, it remains deployed, although you could instead replace the application with a simple page that says something like "not in service."

Unfortunately you cannot disable the app from Cloud shell you should disable it from google cloud console.

1. In the Cloud Console, on the Navigation menu, click App Engine > Settings.
2. Click Disable application.
3. Read the dialog message. Enter the App ID and click DISABLE.
   
If you refresh the browser window you used to view to the application site, you'll get a 404 error.

