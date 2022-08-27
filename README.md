# IdentityChecker-KYC

   It is a source code for checking new customers' backgrounds to figure out, is appropriate to open an account in banks. It has several stages to confirm customer's information. I have used Spark Cluster for the project because process speed is one of the most important parameters. In this document, I will explain all of the stages as well as I can.

## Installation 
  
  **To run the project you have to install some components**
  
  ```
  pip install suds,
  pip install googletrans==3.1.0a0
  ```
  
## Checking Turkish Identification Number
  
   I have used two different validation algorithm. First of them checks, **is the identification number format true?**
   
<p align="center">
  <img width="567" height="543" src="https://user-images.githubusercontent.com/57317518/187026454-b3add436-9a6f-4951-a1a7-7a84b17ed51c.png">
</p>
  

  Second validation algorithm checks, **is the identicication number valid?. The algorithm needs identification number, name, surname and birth year. If your information is incorrect, it return false**
  
<p align="center">
  <img width="1040" height="140" src="https://user-images.githubusercontent.com/57317518/187026260-5b16d06f-8940-42b7-bb90-63f48c7e05d5.png">
</p>

  
<p align="center">
  <img width="765" height="140" src="https://user-images.githubusercontent.com/57317518/187026266-a74eda58-6a6b-4987-9354-280090eea5a0.png">
</p>



## Checking Similarities

 I have created an algorithm to calculate how similar the customers are. It checks customers' similarities by looking at words, and dispersion of words. It counts matched words and total words and calculates total percentage of similarity.


 <p align="center">
  <img width="459" height="513" src="https://user-images.githubusercontent.com/57317518/187026839-6a99be84-8f24-4b4c-9737-dcc8314d2e48.png">
</p>

## Checking Foreign Customers

This project is compatible with foreign customers' information. To provide that point, I used a translator. If the customer's origin is **AR** or **RU**, the algorithm translates to **Latin Alphabet** for the checking with data.

 <p align="center">
  <img width="877" height="230" src="https://user-images.githubusercontent.com/57317518/187027256-a676c314-169c-467d-b8d6-e45108b2594c.png">
</p>



## Processing Data
  
   I have used a Spark Cluster. First of all, I created a schema for the customer data and criminal data, after that, I read all of the data, and created a loop to check similarities between the test customer and all data in the cluster so I got tables about the similarity results.
   
 <p align="center">
  <img width="459" height="513" src="https://user-images.githubusercontent.com/57317518/187027043-b48b8744-f14d-4450-ade6-67bf65555594.png">
</p>


    
  
   


