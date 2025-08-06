# Flask Docker Jenkins Demo

This is a simple Flask application designed to demonstrate CI/CD pipelines using **Jenkins** and **Docker**.

## 🧩 Features

- Python Flask web app
- Returns a basic message: `Hello from Jenkins Pipeline + Docker!`
- Designed for Dockerization and Jenkins pipeline deployment

## 🏗 Project Structure

.
├── app.py # Main Flask application
├── Dockerfile # (You can add this)
├── Jenkinsfile # (You can add this)
└── README.md

bash
Copy
Edit

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone <your-repo-url>
cd <your-repo-name>
2. Install requirements
bash
Copy
Edit
pip install flask
3. Run the application
bash
Copy
Edit
python app.py
It will be available at http://localhost:5000/

4. Docker Support (Optional)
Create a Dockerfile with:

Dockerfile
Copy
Edit
FROM python:3.9-slim

WORKDIR /app

COPY . /app

RUN pip install flask

EXPOSE 5000

CMD ["python", "app.py"]
Then build and run:

bash
Copy
Edit
docker build -t flask-jenkins-demo .
docker run -p 5000:5000 flask-jenkins-demo
🔧 Jenkins Integration (Optional)
Create a Jenkinsfile to automate build and deploy

Use webhooks to trigger on git push

Add stages like Build, Test, Deploy

📞 Output
When you hit the root endpoint (/), it returns:

csharp
Copy
Edit
Hello from Jenkins Pipeline + Docker!