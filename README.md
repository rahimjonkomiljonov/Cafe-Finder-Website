Cafe Finder Website
Overview
The Cafe Finder Website is a Flask-based web application that interacts with the Cafe Finder API to manage and display a list of cafes. Users can view all cafes, search for cafes by location, add new cafes, update coffee prices, and delete cafes. The website provides a user-friendly interface built with Flask, Bootstrap, and WTForms, making it easy to interact with the API.
This project is a great example of how to build a front-end web application that communicates with a RESTful API!
Features

View a list of all cafes or search for cafes by location.
Add a new cafe with details like name, location, and amenities.
Update the coffee price of an existing cafe.
Delete a cafe (requires an API key).
Responsive design using Bootstrap for a better user experience.

Prerequisites
Before you start, make sure you have the following installed:

Python 3.x (preferably Python 3.8 or higher)
pip (Python package manager)
A code editor like Visual Studio Code or PyCharm
The Cafe Finder API running locally (see the API's README for setup instructions)

Setup Instructions
1. Clone or Download the Project
If you're using Git, clone the repository to your local machine:
git clone <repository-url>
cd cafe-finder-website

Alternatively, download the project files and navigate to the project folder.
2. Create a Virtual Environment (Optional but Recommended)
A virtual environment keeps your project’s dependencies separate from other projects.

On Windows:python -m venv venv
venv\Scripts\activate


On macOS/Linux:python3 -m venv venv
. venv/bin/activate



After activation, you’ll see (venv) in your terminal.
3. Install Dependencies
The project requires some Python packages listed in requirements.txt. Install them by running:

On Windows:python -m pip install -r requirements.txt


On macOS/Linux:pip3 install -r requirements.txt



This will install Flask, Flask-Bootstrap5, Flask-WTF, Requests, and other necessary packages.
4. Set Up Environment Variables (Optional)
The website uses a secret key for security and an API base URL to communicate with the Cafe Finder API.

Create a .env file in the project root (optional) or set environment variables directly:FLASK_SECRET_KEY=your-secret-key
API_BASE_URL=http://localhost:5000


If you don’t set these, the app will use defaults:
FLASK_SECRET_KEY: dev-secret-key-123
API_BASE_URL: http://localhost:5000



5. Ensure the Cafe Finder API is Running
The website depends on the Cafe Finder API to function. Make sure the API is running on http://localhost:5000 (or the URL you specified in API_BASE_URL).

Follow the setup instructions in the Cafe Finder API’s README to start the API.

6. Run the Website
Start the Flask web server by running the main script:
python main.py

The website will run on http://localhost:5001 by default. You’ll see a message in the terminal saying the server is running in debug mode.
Using the Website
1. Home Page

URL: http://localhost:5001/
Description: Displays a list of all cafes retrieved from the API. You can also search for cafes by location using the search bar.
Search Example:
Enter a location (e.g., Downtown) in the search bar and click "Search".
The page will show only cafes in that location, or a message if none are found.



2. Add a New Cafe

URL: http://localhost:5001/add
Description: Provides a form to add a new cafe to the database via the API.
Fields:
Cafe Name (required)
Location (required)
Image URL (required)
Map URL (required)
Seats (required, e.g., 20-30)
Coffee Price (optional, e.g., £2.50)
Has WiFi? (checkbox)
Has Power Sockets? (checkbox)
Has Toilet? (checkbox)
Can Take Calls? (checkbox)


Example:
Fill out the form with details like:
Name: The Coffee House
Location: Downtown
Image URL: https://images.example.com/coffeehouse.jpg
Map URL: https://maps.example.com/coffeehouse
Seats: 20-30
Coffee Price: £2.50
Check the boxes for WiFi and Toilet.


Click "Add Cafe". If successful, you’ll be redirected to the home page with a success message.



3. Edit a Cafe’s Coffee Price

URL: http://localhost:5001/edit/<cafe_id>
Description: Allows you to update the coffee price of a specific cafe.
Example:
Navigate to http://localhost:5001/edit/1 (replace 1 with the cafe’s ID).
Enter a new coffee price (e.g., £5.67).
Click "Update Price". If successful, you’ll be redirected to the home page with a success message.



4. Delete a Cafe

URL: http://localhost:5001/delete/<cafe_id>
Description: Allows you to delete a specific cafe, but requires the correct API key.
API Key: The key is TopSecretAPIKey (matches the API’s hardcoded key).
Example:
Navigate to http://localhost:5001/delete/1 (replace 1 with the cafe’s ID).
Enter the API key: TopSecretAPIKey.
Click "Confirm Delete". If successful, you’ll be redirected to the home page with a success message. If the key is wrong, you’ll see an error message.



Project Structure

main.py: The main Flask application file that defines routes and interacts with the API.
templates/: Contains HTML templates for the website:
index.html: Home page with the list of cafes and search form.
add.html: Form to add a new cafe.
edit.html: Form to update a cafe’s coffee price.
delete.html: Form to delete a cafe.


static/: Contains static files like CSS (e.g., styles.css for custom styling).
requirements.txt: Lists the Python packages required for the project.

Dependencies

Flask: Web framework for building the website.
Flask-Bootstrap5: Integrates Bootstrap for responsive design.
Flask-WTF: Handles form creation and validation.
Requests: Makes HTTP requests to the Cafe Finder API.

Notes

The website runs in debug mode (debug=True), which is great for development but should be turned off in production.
The API key for deleting cafes is hardcoded in the API as TopSecretAPIKey. In a real application, you’d want to store this securely (e.g., in environment variables).
Error messages are displayed to the user via flash messages (e.g., “Failed to add cafe” or “Cafe deleted successfully”).

Troubleshooting

Error: “No module named ”Make sure you’ve activated the virtual environment and installed the dependencies (pip install -r requirements.txt).
Error: “Port 5001 is already in use”Another program is using port 5001. Stop the other program or change the port in main.py:app.run(port=5002, debug=True)


Error: “Failed to connect to API”Ensure the Cafe Finder API is running on http://localhost:5000 (or the URL specified in API_BASE_URL). Check the API server’s terminal for errors.
Form Validation ErrorsMake sure all required fields are filled out in the forms (e.g., Cafe Name, Location).

Contributing
Feel free to fork this project, make improvements, and submit a pull request! Some ideas for improvement:

Add more styling to the templates for a better user experience.
Add input validation for fields like coffee price (e.g., ensure it’s a valid currency format).
Improve error handling to show more detailed messages to the user.

License
This project is for educational purposes and doesn’t have a specific license. Feel free to use and modify it as you like!
