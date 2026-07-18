
# ✨ Joy: Your AI Learning Buddy! ✨

## Project Overview

**Joy: Your AI Learning Buddy** is an interactive Streamlit application designed to make learning algorithms fun and engaging. It provides explanations, analogies, and quizzes on various algorithmic concepts, helping users master complex topics with ease. The application is styled with a custom velvet maroon theme and offers the option to include visual references.

## Features

-   **Interactive Learning Modes**: Choose from three engaging modes:
    -   🌟 **Explain it simply!**: Get straightforward explanations of algorithmic concepts.
    -   🍿 **Show me a fun analogy!**: Understand algorithms through relatable stories and comparisons.
    -   🧠 **Challenge me with a friendly quiz!**: Test your knowledge with interactive quizzes.
-   **Customizable Experience**: Toggle visual references (charts/diagrams) on or off.
-   **Elegant UI**: A custom velvet maroon theme provides a visually appealing and distinct user experience.
-   **Algorithm Visualization (Optional)**: When enabled, the application displays a relevant visual aid to enhance understanding.

## How to Run the Application

Follow the steps outlined in the Colab notebook to get Joy up and running:

### Step 1: Install Required Libraries

This step installs all necessary Python packages, including `streamlit` for the web interface, `pyngrok` for creating a public tunnel to your local Streamlit app, and the `google-generativeai` SDK (though mock responses are currently used).

```python
!pip install -q streamlit pyngrok google-generativeai
```

### Step 2: Write the Streamlit Application Script

This cell uses `%%writefile` to create `app.py`, which contains the Streamlit application's core logic. It defines the UI layout, styling, and how the different learning modes interact.

```python
%%writefile app.py
# (Full app.py content as seen in the notebook)
```

### Step 3: Launch the Streamlit Server in the Background

This command starts the Streamlit server in the background, making your `app.py` accessible.

```python
!nohup streamlit run app.py --server.port 8501 &
import time
time.sleep(5)
```

### Step 4: Clear Background Jams and Generate Public URL

This final step ensures no old processes are interfering, sets up `pyngrok` with your authentication token (remember to replace with your actual token), and generates a public URL that you can use to access your running Streamlit application.

```python
from pyngrok import ngrok
ngrok.set_auth_token("YOUR_NGROK_AUTH_TOKEN") # IMPORTANT: Replace with your actual token
try:
    ngrok.kill()
    print("🧹 Successfully cleared old background tunnels!")
except Exception:
    pass
public_url = ngrok.connect(8501)
print("\n👉 SUBMIT THIS PUBLIC LINK TO YOUR CAPSTONE FORM:")
print(public_url)


Once all steps are executed, the public URL printed in the last cell will allow you to interact with Joy: Your AI Learning Buddy in your browser.

## Current Status

The application currently uses mock responses for its learning modes. The architecture is in place for future integration with actual Generative AI models (e.g., Google Gemini) to provide dynamic and context-aware content.

## Technologies Used

-   **Streamlit**: For creating interactive web applications with Python.
-   **Pyngrok**: For exposing local web servers to the internet via secure tunnels.
-   **Python**: The primary programming language.
-   **CSS**: For custom styling (velvet maroon theme).

## Future Enhancements

-   Integration with a live Generative AI model for dynamic content generation.
-   Expansion of learning topics and difficulty levels.
-   User authentication and progress tracking.
-   More diverse visual aids and interactive elements.

```
