<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Customer Support Chatbot README</title>
  
</head>
<body>

<h1>Customer Support Chatbot with RAG & Emotion Intensity Detection</h1>

<p>This repository contains a customer support chatbot that uses Retrieval-Augmented Generation (RAG) to answer user queries based on a custom knowledge base, along with emotion intensity detection for each user message.</p>

<hr />

<h2>Features</h2>
<ul>
  <li><strong>RAG-based retrieval:</strong> Uses FAISS with Sentence Transformers embeddings to find the most relevant answer from a customer support knowledge base.</li>
  <li><strong>Emotion &amp; intensity detection:</strong> Analyzes user input to detect emotions like anger, joy, sadness, fear, and surprise with intensity scores.</li>
  <li><strong>Integrated backend:</strong> FastAPI backend serves both RAG answers and emotion detection results in a single API endpoint.</li>
  <li><strong>Streamlit frontend:</strong> Simple UI for users to chat with the bot and see emotion intensity feedback in real time.</li>
</ul>

<hr />

<h2>Project Structure</h2>
<pre><code>customer_support/
├── backend/
│   ├── rag_module.py       # RAG retrieval logic
│   ├── emotion_module.py   # Emotion + intensity detection
│   ├── main.py             # FastAPI backend server
│   └── data/
│       ├── customer_support.index  # FAISS index file
│       └── customer_support_df.pkl # Knowledge base DataFrame
├── frontend/
│   └── app.py              # Streamlit frontend app
├── requirements.txt
└── README.md
</code></pre>

<hr />

<h2>Setup Instructions</h2>

<h3>1. Clone the repository</h3>
<pre><code>git clone https://github.com/your-username/customer_support_chatbot.git
cd customer_support_chatbot
</code></pre>

<h3>2. Create and activate a virtual environment (optional but recommended)</h3>
<pre><code>python -m venv venv
source venv/bin/activate  # Linux/macOS
venv\Scripts\activate     # Windows
</code></pre>

<h3>3. Install dependencies</h3>
<pre><code>pip install -r requirements.txt
</code></pre>

<h3>4. Prepare the data</h3>
<ul>
  <li>Ensure your FAISS index file (<code>customer_support.index</code>) and knowledge base DataFrame (<code>customer_support_df.pkl</code>) are located inside <code>backend/data/</code>.</li>
  <li>These files contain the indexed customer support Q&amp;A pairs used by the retrieval module.</li>
</ul>

<h3>5. Run the FastAPI backend</h3>
<pre><code>uvicorn backend.main:app --reload
</code></pre>
<p>The backend will start on <code>http://127.0.0.1:8000</code>.</p>

<h3>6. Run the Streamlit frontend</h3>
<pre><code>streamlit run frontend/app.py
</code></pre>
<p>The frontend UI will open in your browser where you can chat with the bot.</p>

<hr />

<h2>Usage</h2>
<ul>
  <li>Type your customer support query in the input box.</li>
  <li>Click "Send" to get an answer from the RAG system.</li>
  <li>The detected emotion intensities of your query will also be displayed.</li>
  <li>New messages appear at the top of the chat window.</li>
</ul>

<hr />

<h2>Model Details</h2>
<ul>
  <li><strong>RAG Embeddings:</strong> Uses <code>all-MiniLM-L6-v2</code> Sentence Transformer model for embedding queries and knowledge base documents.</li>
  <li><strong>Emotion Detection:</strong> Uses a fine-tuned BERT model for multi-label emotion intensity prediction.</li>
  <li><strong>FAISS:</strong> Efficient vector similarity search on the knowledge base.</li>
</ul>

<hr />

<h2>Future Improvements</h2>
<ul>
  <li>Fine-tune embeddings on customer support domain data for better accuracy.</li>
  <li>Add multi-turn conversation context to improve responses.</li>
  <li>Deploy backend and frontend to a cloud platform.</li>
  <li>Add user authentication and chat history storage.</li>
  <li>Integrate human alerting system based on emotion intensity thresholds.</li>
</ul>

<hr />

<h2>License</h2>
<p>This project is licensed under the MIT License.</p>

<hr />

<h2>Contact</h2>
<p>For questions or contributions, please contact <a href="mailto:rachitguptacse.098@gmail.com">rachitguptacse.098@gmail.com</a>.</p>

</body>
</html>
