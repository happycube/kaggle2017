### Instacart Market Basket Analysis code, August 14, 2017

The code posted here is half of my #100 solution - the other half is Sh1ng's features fed directly into a lightgbm model.

I used docker-compose to run the Postgres server, and I created the database from the psql command run inside it - 'CREATE DATABASE insta0811;'  The SQL code produces several different dataframes which are combined within the final model.  

---


I forget who said it first (KazAnova?) that you should learn one new thing each Kaggle Competition you particpate in - in this case I finally took up SQL, which felt like a real hole in my skillset.  I wound up using it for most of my feature engineering.  I found it quite interesting to do FE in a different and ultimately modular way.  I wound up pulling Faron's order streak feature.

My final submission models used lightgbm and xgboost - at the end the latter because I ran out of time to tune lightgbm and xgboost did a better job of picking up the last sets of features I did.  In the end I had 59 features, using "department-as-product" features which didn't add too much.

In hindsight I should have started this a lot earlier (abandoning Sberbank and Mercedes, both of which were too unpredictable for me to tame with my current skills!) and worked on totally original modeling concepts optimized for this competition.  The data was very consistent and CV worked predictably for the first time in a while ;)
