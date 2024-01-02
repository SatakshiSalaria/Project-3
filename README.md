Project Background

Funnel analysis is a method in data analysis used to track and understand the sequential steps or stages that users or customers go through when interacting with a product, service, or website. It's called a "funnel" because the shape of the analysis resembles that of a real-world funnel – wide at the top and narrow at the bottom. However, it could also be easily represented by a bar chart.

Funnel analysis allows businesses and organizations identify where users drop off or convert, helping them to ultimately increase desired outcomes, such as sales, sign-ups, or conversions. It is widely used in e-commerce, marketing, and product development to drive growth and revenue.

Metrocar’s Funnel

The customer funnel for Metrocar typically includes the following stages:
1.) App Download: A user downloads the Metrocar app from the App Store or Google Play Store.

2.) Signup: The user creates an account in the Metrocar app, including their name, email, phone number, and payment information.

3.) Request Ride: The user opens the app and requests a ride by entering their pickup location, destination, and ride capacity (2 to 6 riders).

4.) Driver Acceptance: A nearby driver receives the ride request and accepts the ride.

5.) Ride: The driver arrives at the pickup location, and the user gets in the car and rides to their destination.

6.) Payment: After the ride, the user is charged automatically through the app, and a receipt is sent to their email.

7.) Review: The user is prompted to rate their driver and leave a review of their ride experience.

8.) Similar to other customer funnels, there will be drop-offs at every stage of the funnel, which is why funnel analysis can be helpful in identifying areas for improvement and optimization. For example, Metrocar may analyze the percentage of users who download the app but do not complete the registration process, or the percentage of users who request a ride but cancel before the driver arrives.

Dataset structure

You can find a description of each table and its columns below.

1.) app_downloads: contains information about app downloads

    app_download_key: unique id of an app download
    
    platform: ios, android or web
    
    download_ts: download timestamp
    
2.) signups: contains information about new user signups

    user_id: primary id for a user
    
    session_id: id of app download
    
    signup_ts: signup timestamp
    
    age_range: the age range the user belongs to
    
3.) ride_requests: contains information about rides

    ride_id: primary id for a ride
    
    user_id: foreign key to user (requester)
    
    driver_id: foreign key to driver
    
    request_ts: ride request timestamp
    
    accept_ts: driver accept timestamp
    
    pickup_location: pickup coordinates
    
    destination_location: destination coordinates
    
    pickup_ts: pickup timestamp
    
    dropoff_ts: dropoff timestamp
    
    cancel_ts: ride cancel timestamp (accept, pickup and dropoff timestamps may be null)
    
4.) transactions: contains information about financial transactions based on completed rides:
      
    ride_id: foreign key to ride
      
    purchase_amount_usd: purchase amount in USD
      
    charge_status: approved, cancelled
      
    transaction_ts: transaction timestamp
    
5.) reviews: contains information about driver reviews once rides are completed

    review_id: primary id of review
    
    ride_id: foreign key to ride
    
    driver_id: foreign key to driver
    
    user_id: foreign key to user (requester)
    
    rating: rating from 0 to 5
    
    free_response: text response given by user/requester
