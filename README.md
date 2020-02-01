# TS - Task 4

## Run locally

- Run [application](https://github.com/trustedshops/docker-aspirant)
- `docker exec -it tsas-tools mysql -uroot -pTru5t€d -htsas-db`
- `use company`

## Task

Write the following queries:

1. Select the most recent 10 Buyers ordered by creationDate

   ```sql
   select * from Buyer order by creationDate DESC limit 10;
   ```

1. Select the most recent 10 Buyers having two email addresses and display the email ad-dresses only.

   ```sql
   select email from BuyerEmail inner join Buyer on BuyerEmail.buyer_id = Buyer.id group by email having count(*) > 1 order by Buyer.creationDate desc limit 10;
   ```

1. Select 20 Buyers having done a shop review (Table: BuyerShopReview)

   ```sql
   select * from BuyerShopReview inner join Buyer on BuyerShopReview.buyer_id = Buyer.id where BuyerShopReview.text is not null limit 20;
   ```
