# GCP-DocumentAI

Back in the days organizations and industries used to rely on documentations / forms / memos to store / preserve the information or data. Even today many organizations use documents to store or collect the information. This information needs to be digitized for it to become useful; however, this is usually accomplished through time-intensive, manual processes.
If we look at those documents we can still interpret that data and information but as it's unstructured data it cant be processed or analyzed by the machine. To overcome this challenge there are 2 ways 
Manual data entry - this approach is manual and time consuming as it requires complete human intervention.
AI/ML based approach - Uses Artificial intelligence engine to interpret the document and converts into texts, key-value pair, paragraphs

Google Cloud’s Document AI is one of the best solutions to process your documents. Document AI is a document understanding platform that takes unstructured data from documents and transforms it into structured data, making it easier to understand, analyze, and consume. Document AI uses machine learning and Google Cloud to help you create scalable, end-to-end, cloud-based document processing applications.
![alt text](https://cloud.google.com/static/document-ai/docs/images/document-ai-platform.png)
This diagram illustrates all of the key document processing steps that are supported by Document AI and how they can connect to each other.

Supported formats - JPEG, JPG, PNG, WEBP, BMP, PDF, TIFF, TIF, GIF
Document AI use cases are endless few examples are as below -

Pre-process documents with image quality detection and deskewing
Extract text and layout information from document files
Identify key-value pairs in structured forms
Split and classify documents by type
Extract and normalize entities
Label and review documents
Store, search, organize, govern, and analyze documents and metada



#How Document AI Works?
Processor is a key component of Document AI processor that acts as an interface between the document file and a machine learning model that performs document processing actions. They can be used to classify, split, parse or analyze a document.

Each Google Cloud project needs to create its own processor instances.
Processors fit into one of the following categories:

General - Pre-built processors for compatibility with most documents
Specialized - Pre-built processors for specific document types
Procurement - Documents used for purchases and payments, such as invoices and receipts
Identity - Documents used for identity verification
Lending - Documents used for mortgage loans
Contract - Extract and understand entities from business contracts
Custom - User-created processors for custom documents and use case

#Workflow of Document AI
Here are the major steps to use Document AI to start processing documents:
Choose a processor that is suitable for your use case.
Create a processor using the Cloud console or the Document AI API.
Document AI creates a prediction endpoint where you can send your documents.
Send your document(s) for processing.
Document AI processes the document(s) and returns one or more Document objects, which contain the extracted, structured information.

#Which processor should I use?
To decide what processor type to use for a specific application, here are some general guidelines:
![alt text](https://github.com/Cloud-Evonence/GCP-DocumentAI/blob/main/images/docuai.png)

#Batch Processing
The document AI can process only the input file which has 10 pages or size 20 MBs 
To overcome this limitation there is method called Batch Processing 
The only difference between batch processing and process Document is that instead of sending a single request for a single document, batch processing will send all your documents in a single request. The response will then be stored in a GCS bucket that you have defined on the batch process options.
Using the Batch processing pipeline approach it becomes easy and possible to process larger documents with Document AI
There are sample Python codes to achieve this provided by GCP 

#Sample Architecture
![alt text](https://github.com/Cloud-Evonence/GCP-DocumentAI/blob/main/images/flowv.png)
To automate the process of converting documents into Machine readable format we can use GCP tools and create a pipeline. As seen in this architecture we have used Cloud storage bucket as storage option which will store the input document file as well as processed output word / csv format files at the end of the process. Using cloud function we can create an automated trigger which will get activated every time there is new object is dropped in the cloud storage bucket and send the new document object into the correct Document AI processor 




