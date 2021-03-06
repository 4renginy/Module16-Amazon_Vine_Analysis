# Module16-Amazon_Vine_Analysis

## Purpose of Project

    The purpose of this project is to analyzing Amazon reviews written by members of the paid Amazon Vine program and to to determine
    if there is any bias toward favorable reviews from Vine members in the dataset.
    
    The Amazon Vine program is a service that allows manufacturers and publishers to receive reviews for their products. 
    Companies like SellBy pay a small fee to Amazon and provide products to Amazon Vine members, who are then required to publish
    a review.

    In this project, we had access to approximately 50 datasets. Each one contained reviews of a specific product, from clothing apparel
    to wireless products. I have picked "Amazon reviews_us_Electronics"

    
    using  PySpark (ETL process) 
    extracted the Electronics dataset, 
    transformed the data, 
    connected to an AWS RDS instance, and 
    loaded the transformed data into pgAdmin. 
    
  

   ## Process:

   1- Perform ETL on Amazon Product Reviews
    
   [Amazon_Reviews_ETL.ipynb file](https://github.com/4renginy/Module16-Amazon_Vine_Analysis/blob/main/Amazon_Reviews_ETL.ipynb)


                I)Started with importing electronics data into colabotary 
                
                II)Turned the dataset into dataframe called review_id_df

                III) Created following tables to analyse;

                        a-customers_df
                        b-products_df
                        c-review_id_df
                        d-vine_df

                IV)Connected to AWS RDS and wrote each of those data frames to its table 

                At the end of this process we had all the tables at pgadmin sql database to be analysed.
  ![](https://github.com/4renginy/Module16-Amazon_Vine_Analysis/blob/main/sql.JPG)

    
    2- Determine Bias of Vine Reviews
    
  [Vine_Review_Analysis.ipynb](https://github.com/4renginy/Module16-Amazon_Vine_Analysis/blob/main/Vine_Review_Analysis.ipynb)

               In this file we have uplaoded the electronics file into colaboratory, 

               created a dataframe from the full data

               created vine_df with 6 required colums for the analysis

                then filtered the data for
                                            1-"total_votes>=20 
                                            2-"helpful_votes/total_votes>=0.5"

                Now the preperations are over and we can start calculating
                                            
                    Total count of 5 star readings                      23497
                                         five star from nonvinemembers  23043
                                         five star from vinemembers       454

                    Total Count of nonvine club ratings                 49673
                     Count of wine club member ratings                   1080
                        
                    Five star percentage for nonvine club members      46.39 %
                    Five star percentage for wine club members         42.03 %

Conculution 1: Based on our calculations five star percentage from nonwine club memebers is higher than wine 
club members, that shows no bias for the vine program

However we wanted to make sure the concution withdrow is accurate went one step ahead and run more calcuations by 
including verified purchase.

                Percentage of five star ratings for nonvine members with verified purchases:         48.06 %

                Percentage of five star for ratings for nonvine members with uverified purchases:    44.56 %

                Percentage of five star ratings for vinemembers with verified purchase:               100 % 

                Percentage of five star ratings for vinemembers with unverified purchases:           41.87 %

Concuclution 2: Percentage of nonvine members voting 5 star still higher for nonmembers. !00 % for verifed vinemembers however there is only3 votes
so we could condiser it as swing vote

 

## CONCULUTION:
Based on calculations we made for the number of members and nonmembers with 5 star ratings;

**********************there is any bias toward favorable reviews from Vine members in the dataset*******************

Thank you for your time
