## 📄Types of PDFs

Before we begin, let's understand what PDF files are and how they are structured. We'll start with the fact that there are two types of PDF files: Native and scanned

## 💻Native PDF

A PDF file that is originally generated in a computer, aka "born digital", meaning that it was created from an original electronic version of a document. One quick way to tell that a PDF is native is that you can select blocks of text in the file. 

## 🖨️Scanned PDF

A PDF file that is made up of scanned images of a given document. With scanned PDFs you will not be able to select text or use the search function because the PDF is a collection of images. 

In PDF automation, data can be extracted using two separate activities: 

1. Extract data using Read PDF Text activity. 

2. Extract data using Read PDF with OCR activity. 

Read PDF Text is the more accurate of the two but works only with native PDF documents. Read PDF with OCR is less reliable but can extract text from scanned PDF documents. The second option also requires the selection of an OCR engine. 

 Both activities are available in the **UiPath.PDF.Activities** package.

![[Pasted image 20250504155205.png]]