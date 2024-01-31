# homework-zoomcamp-1


This for answer homework for data-engineer-zoompcamp year 2024
https://github.com/DataTalksClub/data-engineering-zoomcamp

1. --rm
   
   ![image](https://github.com/mysecret39/homework-zoomcamp-1/assets/88777199/725e8b0e-c327-46ca-a429-5cdd3ba6a35f)

2. 0.42.0

3. 15612

```bash
   SELECT COUNT(*) FROM green_taxi WHERE CAST(lpep_dropoff_datetime as date)= '2019-09-18' AND CAS
 T(lpep_pickup_datetime AS date) = '2019-09-18'
```
![image](https://github.com/mysecret39/homework-zoomcamp-1/assets/88777199/564e3aec-f953-452a-9d8f-b017fff00b79)

4. 2019-09-26
```bash
   SELECT MAX(trip_distance), CAST(lpep_pickup_datetime AS DATE) FROM green_taxi GROUP BY lpep_pic
 kup_datetime ORDER BY max DESC limit 10
```
   ![image](https://github.com/mysecret39/homework-zoomcamp-1/assets/88777199/128acd63-9607-41d6-b231-06b497ac9150)

5. "Brooklyn" "Manhattan" "Queens"
   ![image](https://github.com/mysecret39/homework-zoomcamp-1/assets/88777199/f873dee1-cfd2-4f2c-b967-455541e33fa4)

6. JFK Airport
```bash
   SELECT z."Zone" AS drop_off_zone_with_largest_tip
FROM green_taxi gt
JOIN zone z ON gt."DOLocationID" = z."LocationID"
WHERE gt."PULocationID" = (SELECT "LocationID" FROM zone WHERE "Zone" = 'Astoria')
  AND EXTRACT(YEAR FROM gt."lpep_pickup_datetime") = 2019
  AND EXTRACT(MONTH FROM gt."lpep_pickup_datetime") = 9
ORDER BY gt."tip_amount" DESC
LIMIT 1;
```

   ![image](https://github.com/mysecret39/homework-zoomcamp-1/assets/88777199/2220b61a-c210-4a35-9108-0f6e098ca649)

