Based on the project files you've provided, here is a README file for a GitHub repository.

### **Project Title: COVID Bed Slot Booking System**

-----

### **Overview**

This is a web-based application for managing COVID-19 bed slot bookings. It's built using the **Flask** framework and connects to a **MySQL** database. The system allows users to book hospital beds, and provides hospital administrators and a central admin with the tools to manage bed availability and view patient details.

-----

### **Features**

  * **User Module**: Users can sign up and log in using their SRF ID and date of birth. They can then book a bed slot by providing their details, and they can view their booking information.
  * **Hospital User Module**: Hospital administrators can log in with their assigned hospital code, email, and password. Once logged in, they can add or update their hospital's bed availability, including normal, HICU, ICU, and ventilator beds.
  * [cite\_start]**Admin Module**: A super-admin can log in with predefined credentials (username: `admin`, password: `admin`)[cite: 1]. The admin can add new hospital users to the system, granting them access to manage their hospital's data.
  * **Database Management**: The system uses a MySQL database to store information about users, hospitals, bed bookings, and hospital users.
  * **Triggers**: The database includes triggers that log `INSERT`, `UPDATE`, and `DELETE` operations on the `hospitaldata` table into a separate `trig` table. This provides a history of changes to hospital bed information.

-----

### **System Requirements**

To run this project, you will need to have the following installed:

  * **Python 3.x**
  * **XAMPP** (or a similar environment) with **PHPMyAdmin** and **MySQL**

-----

### **Installation and Setup**

1.  **Clone the repository**:

    ```bash
    git clone <repository-url>
    cd <repository-folder>
    ```

2.  **Install Python dependencies**:

    ```bash
    pip install -r requirements.txt
    ```

    [cite\_start]This will install Flask, Flask-SQLAlchemy, Flask-Login, and Flask-Mail, along with other necessary libraries[cite: 2].

3.  **Database Setup**:

      * Open XAMPP and start the Apache and MySQL modules.
      * Go to `http://localhost/phpmyadmin` in your browser.
      * Create a new database named `covid`.
      * Import the `covid.sql` file provided in this repository into the `covid` database. This will create all the necessary tables, stored procedures, and triggers.

4.  **Run the application**:

    ```bash
    python main.py
    ```

5.  **Access the application**:

      * The application will be running on `http://127.0.0.1:5000` (or another port if 5000 is in use).

-----

### **Usage**

  * **Admin Login**: Navigate to `/admin` and log in with the default credentials (`admin`/`admin`) to add new hospital users.
  * **Hospital Login**: Hospital users can log in at `/hospitallogin` using the credentials created by the admin to manage their hospital's bed data.
  * **User Login**: Patients can sign up at `/signup` and then log in at `/login` to book a bed slot.

-----

### **Project Structure**

  * `main.py`: The main Flask application file. It contains all the routes, database models, and application logic.
  * `covid.sql`: The database dump file for setting up the MySQL database, including schema, tables, triggers, and stored procedures.
  * `templates/`: This folder contains all the HTML files for the web pages (e.g., `index.html`, `usersignup.html`, `hospitallogin.html`, etc.).
  * `requirements.txt`: Lists all the Python libraries required to run the project.
  * `config.json`: (Not included in the provided files but mentioned in the code) This file is intended for storing configuration parameters, such as Gmail credentials for sending emails. You will need to create this file if you want to use the email functionality mentioned in the `main.py` code.

-----

### **ER Diagram**

An ER diagram is included in the repository to provide a visual representation of the database schema and table relationships.
