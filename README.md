# NLP_LEARNING_CRUX 
https://www.linkedin.com/in/sagarika-shah
Frequently asked NLP MCQ &amp; Coding questions! 

Part 1: Multiple Choice Questions

1.1: In the context of NLP, what does tokenization involve? 
a) Converting text into binary format 
b) Splitting text into sentences 
c) Splitting text into words or subwords💡🚀
d) Assigning tags to words 

1.2: What is the main advantage of Convolutional Neural Networks (CNNs) over Fully Connected Neural Networks in image analysis tasks? 
a) They require less computational resources 
b) They are easier to train 
c) They can capture spatial information 💡🚀
d) They can process images of varying sizes 


1.3: What is "Stemming" in NLP? 
a) Process of converting speech into text 
b) Process of reducing words to their root or base form 💡🚀
c) Process of understanding the sentiment of a sentence 
d) Process of converting text into speech 

1.4: What is "Word Embedding" in NLP? 
a) Encoding words or phrases as numerical vectors💡🚀
b) Embedding text in an application
c) Inserting words in a sentence 
d) Translating words into another language

1.5: What is "Latent Dirichlet Allocation (LDA)" used for in NLP? 
a) Translation between languages 
b) Text generation 
c) Sentiment Analysis 
d) Topic Modeling 💡🚀

1.6: What is a "Stop Word" in the context of NLP? 
a) A word that is stopped from being translated 
b) A word that is to be ignored in text analysis 💡🚀
c) A word that stops a program from running 
d) A word that a user has decided to stop using 


2.1: Text Processing 📝🔍🔄
Using the Python library NLTK, write a function that accepts a string and performs the
following:
● Tokenizes the string into words
● Tags parts of speech (POS) for each word
● Performs named entity recognition (NER)
● Counts the frequency of each named entity in the text
CODE-https://www.linkedin.com/in/sagarika-shah
🌸🌺🌻__________________________________________________________________________________🌻🌼🌷
pip install nltk
nltk.download('punkt')
nltk.download('averaged_perceptron_tagger')
nltk.download('maxent_ne_chunker')
nltk.download('words')
import nltk
from nltk.tokenize import word_tokenize
from nltk.tag import pos_tag
from nltk.chunk import ne_chunk

def analyze_text(text):
    # Tokenize the string into words
    tokens = word_tokenize(text)

    # Tag parts of speech (POS) for each word
    pos_tags = pos_tag(tokens)

    # Perform named entity recognition (NER)
    ner_tags = ne_chunk(pos_tags)

    # Count the frequency of each named entity
    entity_counts = {}
    for chunk in ner_tags:
        if hasattr(chunk, 'label'):
            entity = ' '.join(c[0] for c in chunk.leaves())
            entity_label = chunk.label()
            if entity_label not in entity_counts:
                entity_counts[entity_label] = {}
            if entity not in entity_counts[entity_label]:
                entity_counts[entity_label][entity] = 0
            entity_counts[entity_label][entity] += 1

    return entity_counts

# Example usage
text = "Apple Inc. is a technology company headquartered in Cupertino, California. It was founded by Steve Jobs, Steve Wozniak, and Ronald Wayne."
result = analyze_text(text)
print(result)
🌸🌺🌻___________________________________________________________________________________🌻🌼🌷

3.1: PDF Processing and Table Extraction📄🔄📊
Using Python and any library of your choice (such as Tabula, PDFplumber, etc.), write a
function that accepts a path to a PDF file and:
● Extracts all the text from the PDF
● Identifies and extracts tables from the document
● Identifies and extracts all headings in the document
CODE-https://www.linkedin.com/in/sagarika-shah
🌸🌺🌻_____________________________________________________________________________________🌻🌼🌷
pip install pdfplumber
pip install tabula-py
!pip install PyPDF2
!pip install camelot-py[cv]
def extract_text_from_pdf(path):
    with pdfplumber.open(path) as pdf:
        text = ""
        for page in pdf.pages:
            text += page.extract_text()
    return text
pdf_path = "/content/Test.pdf"
extracted_text = extract_text_from_pdf(pdf_path)
print(extracted_text)
tables = tabula.read_pdf(pdf_path, pages='all')  # Use Tabula
# or
with pdfplumber.open(pdf_path) as pdf:
    tables = []
    for page in pdf.pages:
        tables += page.extract_tables()  # Use PDFplumber
import re

headings = re.findall(r'\n(\w+)\n', extracted_text)  # Example regex pattern
print(headings)
🌸🌺🌻_____________________________________________________________________________________🌻🌼🌷
