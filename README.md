Surf's Up
Surf's Up with Data Storage and Retrieval

Overview
The purpose of this analysis was to collect weather information for an investor before they committed to building a new Surf and Ice Cream shop. The investor was concerned with the precipitation in the area and it causing the shop to be closed too often. For the analysis of Hawaii's weather data, we used SQLAlchemy to query the SQLite database.


Results
  * The mean temperature for June was 75 degrees, while for December it was only 71 degrees. With this is mind, one could assume that more people would be in the mood for        surfing or ice cream
  * The minimum	temperature for June was only 64 degrees, while December can in at 56 degrees. Which having a temp that low would stop most from either wanting to surf, or eat       ice cream in the month of December.
  * With the temperatures in June ranging from 64-85 degrees, I could see people being open to surfing and eating ice cream for the entirety of the month.

December Summary

![image](https://user-images.githubusercontent.com/88358771/140629013-40fc26cf-f9fa-48c2-9516-a39a12a984d7.png)

June Summary

![image](https://user-images.githubusercontent.com/88358771/140629024-06cab4b6-ecac-4902-8c6f-1fb64347544e.png)



Summary
The client was worried about the weather temperatures, and precipitation for the location to ensure that the stall would be open enough to make money to be a worthwhile investment. With the data collected for the month of June, I would safely say that the weather would be nice enough for the stall to be open all month long with a steady flow of customers. The temperatures ranged from a low of 64 degrees, up to a high of 85. For the month of December however, with the temperatures dropping to a low of 56, it puts the stall at a higher risk of being closed. As long as the weather stayed in the top 50 percentile at 71 degrees it would be warm enough to stay open. In summation, with the data collected I would be able to safely tell the investor that the stall would be able to stay open enough to safely be considered a fruitful investment.


Queries to gather more data

June Precipitation

june_temp_prec = session.query(Measurement.tobs,Measurement.prcp).filter(extract('month', Measurement.date) == 6).all()

june_temp_prec_df = pd.DataFrame(june_temp_prec)

print(june_temp_prec_df)

june_temp_prec_df.describe()




December Precipitation

dec_temp_prec = session.query(Measurement.tobs,Measurement.prcp).filter(extract('month', Measurement.date) == 12).all()

dec_temp_prec_df = pd.DataFrame(dec_temp_prec)

print(dec_temp_prec_df)

dec_temp_prec_df.describe()
