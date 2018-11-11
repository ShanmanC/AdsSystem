# AdsSystem

Database Schema: 
  Advertiser 
    advertiser id (unique) => long
    name => string 
    budget => double
  Ad 
    ad id (unique) => long
    bid amount => double
    ad image => string
    advertiser id (foreign key) => long
    quality score, a ratio between 0 to 1 => double
  APIs: 
    POST 
      create an ad 
      create an advertiser 	
    UPDATE
      update advertiser budget, increase/decrease value
      update ad bid amount
      *update ad image
    GET
      get an ad based on bidding rule -> return ad id
			  steps:
          check if advertiser still have budget, if not, do not enter bidding stage
          otherwise, for each ad in the system, calculate bid amount * quality score
          choose the ad with max ad rank
          deduct budget from ad accounts that enter bidding stage
        
