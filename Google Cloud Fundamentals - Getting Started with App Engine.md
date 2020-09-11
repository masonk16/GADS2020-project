# LAB : Google Cloud Fundamentals: Getting Started with App Engine


## OBJECTIVES:

    - In this lab, you learn how to perform the following tasks:

    - Initialize App Engine.

    - Preview an App Engine application running locally in Cloud Shell.

    - Deploy an App Engine application, so that others can reach it.

    - Disable an App Engine application, when you no longer want it to be visible.

## STEPS:

1. Initialize App Engine

    - Initialize your App Engine app with your project and choose its region:

        gcloud app create --project=$DEVSHELL_PROJECT_ID

    - Clone the source code repository for a sample application in the hello_world directory:
    
        git clone https://github.com/GoogleCloudPlatform/python-docs-samples

    - Navigate to the source directory:

        cd python-docs-samples/appengine/standard_python/hello_world

2. Run Hello World application locally

    - Execute the following command to download and update the packages list.

        sudo apt-get update

    - Set up a virtual environment in which you will run your application.
        
        sudo apt-get install virtualenv

        If prompted [Y/n], press Y and then Enter.

        virtualenv -p python3 venv

    - Activate the Virtual Environment
        
        source venv/bin/activate

    - Navigate to your project directory and install dependencies

        pip install  -r requirements.txt

    - Run the application
    
         python main.py

3. Deploy and run Hello World on App Engine

    - Navigate to the source directory

        cd ~/python-docs-samples/appengine/standard_python/hello_world

    - Deploy your Hello World application

        cloud app deploy

        If prompted "Do you want to continue (Y/n)?", press Y and then Enter

    - Launch your browser to view the app at http://YOUR_PROJECT_ID.appspot.com

        gcloud app browse

