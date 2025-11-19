Image Category Mismatch: 

Business Requirement: 

The Category Mismatch module for the GeM portal addresses issues of products being incorrectly 
classified into categories, either due to intentional miscategorization or unintentional errors by sellers. 
The goal is to identify products whose images do not align with their assigned categories, thus 
enhancing buyer trust and improving the quality of product listings on the portal. The model analyzes 
product images and classifies whether they fit within the selected category, flagging any anomalies or 
potential manipulations. 

Proposed Solution: 

The solution involves using a CNN model to categorize products based on images. The trained model is 
capable of classifying images into the correct categories and flagging products that do not match their 
designated category as anomalies. 

Solution Consumption: 

1. Market Sanitization:- The module contributes to the Market Sanitization process by continuously 
monitoring and analyzing product images across the marketplace. It identifies and highlights 
products that do not meet the specified category alignment. Detailed reports will be generated for 
GeM SPV, showcasing discrepancies between product images and their respective categories. This 
allows for timely intervention and maintenance of marketplace integrity. 
2. Quality Gate(CMS):- The Category Mismatch module is currently being used in the Catalog 
Management System (CMS). It automatically checks whether the product images match their 
assigned categories. When the module finds mismatches, it flags these products for review. This 
helps to ensure that products are listed correctly, reducing errors and preventing sellers from 
intentionally placing items in the wrong categories. This keeps the platform accurate and easier to 
use for buyers.

Data: 
The required image data can be fetched from below tables to detect the anomalies present in the 
categories in GeM marketplace: 
• inb_variants 
• inb_images 

Model Methodology: 

The Category Mismatch Detection Module utilizes deep learning to identify products whose images 
don't match their assigned categories. The methodology involves: 
1. Data Collection:  
Uses product images from the GeM portal and external e-marketplaces, organized by category.
2. Data Preprocessing:  
Images are resized to 224x224 pixels, with data augmentation applied to ensure a balanced dataset 
across all categories. 
3. Model Training: 
A CNN model is trained for multi-class classification. It uses convolutional layers, pooling, dropout, 
and dense layers. The Adam optimizer is employed, and models are trained for 6 epochs. 
4. Model Dictionary:  
A dictionary links categories to their trained model paths, allowing the correct model to load for 
evaluation. 
5. Evaluation:  
For each product image, the relevant model is loaded, and predictions are made. If the confidence 
score is below 0.08, the product is flagged as an anomaly. 
6. Report Generation: 
Results are saved as reports, identifying images that potentially mismatch their assigned category.
 
Steps In Model: 

1. Data Collection: 
Gather images from GeM database. 
2. Data Preprocessing: 
Resize images and apply augmentation for balance. 
3. Model Training:  
Train CNN models for category-based image classification. 
4. Prediction:  
Load the relevant model, predict the category, and flag anomalies based on confidence scores. 
5. Report Generation:  
Create reports detailing potential mismatches.

Business Value: 

1. Improving Buyer Experience:  
Ensuring that buyers see accurately categorized products increases trust and satisfaction. 
2. Automation of Category Validation:  
The module reduces manual intervention, speeding up the product approval process. 
3. Fraud Prevention:  
By detecting intentional miscategorization, the module helps in preventing fraudulent listings.
4. Compliance with Standards:  
Ensures that product categories adhere to the guidelines set by the GeM portal, enhancing overall 
platform reliability.
![Image Category Mismatch](https://github.com/user-attachments/assets/f97164ea-b5bb-49a0-9402-4059e0189f31)
![Unstructured data analysis -Image Category mismatch ](https://github.com/user-attachments/assets/a764d4ee-9bc4-41b0-82bb-7321d3386dc9)


