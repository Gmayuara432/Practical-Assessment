import requests

def check_application(url):
    try:
        response = requests.get(url)
        if response.status_code == 200:
            print("Application is UP")
        else:
            print("Application is DOWN")
    except requests.ConnectionError:
        print("Failed to connect to the application")

# URL of the application to check
application_url = "http://example.com"

# Check application status
check_application(application_url)
