<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Celery Django Project</title>
</head>
<body>
    <h1>🚀 Celery Django Project</h1>
    <p>A sample project for learning Celery with Django implementing asynchronous and scheduled email sending.</p>

    <hr>

    <h2>📌 Features</h2>
    <ul>
        <li>Asynchronous email sending</li>
        <li>Task scheduling with Celery Beat</li>
        <li>Monitoring with Flower</li>
        <li>Django integration</li>
    </ul>

    <h2>🛠️ Prerequisites</h2>
    <ul>
        <li>Python 3.8+</li>
        <li>Redis (installed locally)</li>
        <li>Git</li>
    </ul>

    <h2>🚀 Project Setup</h2>
    <ol>
        <li>Clone repository:
            <pre><code>git clone https://github.com/Erfan-aminian/Celery.git
cd celery-django-project</code></pre>
        </li>
        <li>Install requirements:
            <pre><code>python -m venv venv
source venv/bin/activate  # Linux/Mac
# or venv\Scripts\activate  # Windows
pip install -r requirements.txt</code></pre>
        </li>
        <li>Environment variables:
            <pre><code>DEBUG=True
SECRET_KEY=your-secret-key
EMAIL_HOST=your-email-host
EMAIL_PORT=587
EMAIL_USE_TLS=True
EMAIL_HOST_USER=your-email
EMAIL_HOST_PASSWORD=your-password</code></pre>
        </li>
        <li>Run migrations:
            <pre><code>python manage.py migrate</code></pre>
        </li>
        <li>Start Django server:
            <pre><code>python manage.py runserver</code></pre>
        </li>
    </ol>

    <h2>📄 Usage Examples</h2>
    <h3>Async Email Task:</h3>
    <pre><code>from emails.tasks import send_welcome_email

# In Django view:
send_welcome_email.delay("user@example.com")</code></pre>

    <h3>Scheduled Task (every 5 minutes):</h3>
    <pre><code># In config/celery.py
app.conf.beat_schedule = {
    'debug-task': {
        'task': 'emails.tasks.debug_task',
        'schedule': 300.0,
    },
}</code></pre>

    <h2>📊 Monitoring</h2>
    <p>Flower Dashboard: <a href="http://localhost:5555">http://localhost:5555</a></p>
    <pre><code>celery -A config flower --port=5555</code></pre>

    <h2>🚦 Running Workers</h2>
    <p>Start Celery Worker:</p>
    <pre><code>celery -A config worker --loglevel=info</code></pre>
    
    <p>Start Celery Beat:</p>
    <pre><code>celery -A config beat --loglevel=info</code></pre>

    <h2>🤝 Contributing</h2>
    <ol>
        <li>Fork the repository</li>
        <li>Create new branch: <code>git checkout -b feature/your-feature</code></li>
        <li>Commit changes: <code>git commit -m 'Add some feature'</code></li>
        <li>Push to branch: <code>git push origin feature/your-feature</code></li>
        <li>Open a Pull Request</li>
    </ol>

    <h2>📜 License</h2>
    <p>MIT License - See <a href="LICENSE">LICENSE</a></p>

    <h2>👏 Acknowledgments</h2>
    <ul>
        <li>Official <a href="https://docs.celeryq.dev/">Celery Documentation</a></li>
        <li><a href="https://www.djangoproject.com/">Django Project</a></li>
    </ul>
</body>
</html>
