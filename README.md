# Flask File Server

This project is a Python script that sets up a simple file server using Flask and Waitress.

---

## Libraries Used

The following Python libraries are used.  
**Please ensure they are installed beforehand.**

- **Flask**  
  Flask is a lightweight web framework.  
  Installation command:  
  ```bash
  pip install flask
  ```
  
- **Waitress**  
  Waitress is a production-ready WSGI server for Python applications.  
  Installation command:  
  ```bash
  pip install waitress
  ```

---

## Configuration File (`config.properties`)

The `config.properties` file is used to configure the server. It follows the `key: value` format.  
Below is an example configuration:

```properties
host: 127.0.0.1  # The host to bind the server to
port: 8080       # The port to bind the server to

# Paths to files and their corresponding endpoints
/files/example: /path/to/example.txt
/files/image: /path/to/image.png
```

### Key Details:
1. `host` and `port`: Define the server's host and port.
2. Other keys are endpoint paths (e.g., `/files/example`) mapped to the file system paths (e.g., `/path/to/example.txt`).

---

## Setup

1. Clone the repository:
   ```bash
   git clone <repository_url>
   cd <repository_name>
   ```

2. Create a `config.properties` file in the root directory based on the format above.

3. Install the required libraries:
   ```bash
   pip install flask waitress
   ```

4. Run the script:
   ```bash
   python <script_name>.py
   ```

---

## Notes

- Ensure the paths in the `config.properties` file are valid and accessible by the server.
- If a file cannot be accessed due to permission issues, the server will return a `403 Forbidden` response.
- If a file is not found, the server will return a `404 Not Found` response.
- To use this server in a production environment, make sure to secure it properly (e.g., using a reverse proxy like Nginx).

---

## Example

### Sample `config.properties`:
```properties
host: 0.0.0.0
port: 5000

/files/text: C:/example_folder/sample.txt
/files/image: C:/example_folder/sample.png
```

### Expected Behavior:
- Accessing `http://0.0.0.0:5000/files/text` will return the contents of `sample.txt`.
- Accessing `http://0.0.0.0:5000/files/image` will return the image `sample.png`.
