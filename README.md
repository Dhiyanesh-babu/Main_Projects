# NOTIFY - Students Notes Taking App

## Description

The web app NOTIFY is designed to address the challenges faced by students who are unable to attend all lectures or struggle to remember important points. Taking comprehensive notes throughout the semester becomes essential, but it can be difficult to search for specific topics in a traditional notebook. NOTIFY aims to solve these issues by utilizing modern web development technologies and Natural Language Processing (NLP).

NLP allows computers to communicate with humans in their own language, enabling them to read text, interpret speech, measure sentiment, and determine important parts of the content. By leveraging NLP, NOTIFY can analyze large amounts of unstructured data, such as lecture notes, in a consistent and unbiased manner.

## Existing System Limitations

Existing note-taking web and mobile apps often rely on topic-based searches, which may not be useful when searching for specific words or phrases. Some applications search the entire document, leading to time and resource consumption if a student needs to search multiple times. Furthermore, models trained in specific subjects like biology, chemistry, or physics may provide advanced definitions that are not suitable for students at lower grade levels.

To overcome these limitations, NOTIFY has developed a model specifically trained based on the student's class lectures. This ensures that the student receives exactly what their faculty has taught, providing valuable support for exam preparation.

## Functionalities of our Model

NOTIFY incorporates various functionalities to enhance the student's note-taking experience:

### A) Text-to-Speech

The app accepts an audio file as input and converts it into a transcript (text file). We utilize the "speech_recognition" library for this process. Additionally, we use the "fullstop-punctuation-multilang-large" model from Hugging Face to handle punctuation, as it is crucial for the summarization process.

### B) Abstractive Summarization

Abstractive summarization involves generating novel sentences by rephrasing or using new words. This technique aims to improve coherence and eliminate redundancies. NOTIFY employs the T5 model (Text-to-Text Transfer Transformer) for abstractive summarization. T5 treats various tasks, including translation, question answering, and classification, as text-to-text transformations, training the model to generate target text for each task.

### C) Extractive Summarization

Extractive summarization identifies salient information by extracting and grouping together important sentences to form a concise summary. The process involves determining the importance of words within sentences and the importance of sentences within the document. The top-ranked sentences are combined in a logical order to create a short summary. For this task, we utilize the English language class from the Spacy library, which provides rules for tokenization, stop words, and sentence analysis.

### D) Keyword Extraction

Keyword extraction automatically identifies the most used and important words and expressions from a text, aiding in summarizing the content and recognizing the main topics discussed. NOTIFY employs the DistilBERT model for keyword extraction. DistilBERT is a compact and efficient Transformer model based on the BERT architecture. It uses knowledge distillation during pre-training to reduce the model size by 40%.

### E) Text Generation

Text generation is the task of automatically generating natural language texts that appear indistinguishable from human-written text. NOTIFY utilizes a fine-tuned GPT-2 model for text generation. GPT-2 is a deep learning transformer-based language model created by OpenAI. It performs unsupervised and supervised learning to learn text representations for NLP downstream tasks. The model predicts the next word(s) in a sentence.
