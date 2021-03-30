## Ford GoBike Data Communication: A Story

## My Dataset

I chose this dataset specifically because I am an avid bike rider, and often wonder if systems like this are useful in any way. Combined with my interest in urban planning, it was a no brainer. I need to do figure out how to calculate the ages of each rider currently, and then do the same for distance. This way I'll be able to see all of the strands of this specific thread of the datasets rope.

This dataset has collected information from 183,412 riders/users regarding their gender, user type, age, distance traveled, duration of each ride, as well as: Start and End addresses and their GPS locations, User ID, location ID, etc. This dataset was provided to me via Udacity. [here](https://video.udacity-data.com/topher/2020/October/5f91cf38_201902-fordgobike-tripdata/201902-fordgobike-tripdata.csv)

## What Did I Find?

I spent some time reading through the csv before actually doing any explorations with pandas. Once I had a basic understanding of the dataset I knew I needed to isolate very specific values that don't necessarily exist originally. Once I cleaned the initial dataset, I first decided to go with a low hanging fruit exploration. 

Although I explored these two variables last, I've found that `user_type` and `member_gender` were going to be two of the most important components in this exploration. When I explored them separately, I found what was expected based on societal standards. I had found that the majority of riders were male subscribers to the bikeshare system, a significant difference from female subscibing riders, and even more so for subscribing riders who identified as "other". This was even more so the case for all riders who were considered customers.

`duration_sec` was the first of three numerical values I decided to explore. Based on the number of trips in total, it was apparent that the majority of the trips were less than 2000 seconds (approx. 30 mins). As I dove deeper, I saw that the majority of trips were somewhwere between 3 and 6 mins. Initially I wasn't sure how this was going to help my analysis moving forward, and truthfully, it doesn't assist my exploration much, aside from being a great control variable. `duration_sec` if anything, showed the truest of colors when compared against both `user_type` and `member_gender`.

To find age, I first scrubbed the dataset of any riders who had a `member_birth_year` that was older than 1940. I thought it prudent to be age inclusive, but also realistic about the human body (which I felt 80 years old would be a more-than-generous middle ground). Once I cleared the dataset of unusuable data, I then subtracted each riders birth year from 2021. That data funnelled into the new column/numerical value, `age`. Exploring `age` was super helpful, and the further I explored, the more interesting things got. I learned that the majority of users were in the mid 30's- late 40's age range. And, that there was a significant amount of riders in the 60s and 70s age range as well. Definitely more than I expected!

`age` definitely helped me find some of the answers I was looking for. When I compared it to `user_type` and `member_gender` I realized that `age` was going to be a major variable I looked into. Due to this, I was able to find that the age ranges between `user_type` were not very different. It also helped me realize that `user_type` was going to be less important in this analysis than `member_gender` as the difference in values represented in age were significant. This is where I started to notice some anomalous-like behavior in the `member_gender`, other, value. It started showing a stronger relationship with `age` than the binary gender types. You can see that the range is much wider for it being the smallest category in `member_gender`. 

Lastly, I wanted to explore a variable that had not existed entirely yet, distance traveled. To calculate distance traveled I had to utilize the haversine vector formula. I searched far and wide for some assistance via the internet, and eventually found that there was no one answer. So I began attempting each way I found, and then comparing different code blocks to see which were most applicable to my dataset. What I landed on, a [stackedoverflow](https://stackoverflow.com/questions/4913349/haversine-formula-in-python-bearing-and-distance-between-two-gps-points) page, was probably the MOST helpful of them all. Once I fully understood what I needed to do, I introduced `distance` into the dataset, and I was surely proud and also glad I had done so, because it was also another super helpful variable in my exploration.

`distance` helped me figure out was `duration_sec` was **trying** to tell me. Which was most of the trips were less than 5 miles, with a majority of them being in between 0.3 miles and 1.5 miles. I also noticed a similar relationship with `member_type` that I saw in `age` representation. The, "Other", category again had a wider range of distances traveled, clocking in distances anywhere from 0.5 miles to 5.5 miles traveled. This helped me decide to specifically focus on how riders' genders and ages affected the distance travled. If you look into my exploration, you can see that `distance` between the genders is about the same. It is a great dependent variable, with age being an even better independent variable. 

All in all, I learned a great deal about this program, and would definitely have some key solutions to getting more use out of the system by San Francisco's residents.

## Main Takeaways

Some key takeaways from this project would be: 
    
   1. **MAIN**: I focus specifically on the relationships between `member_gender`, `age`, and `distance` in my explantory slide deck. There are two slides that include `user_type` variables, but that is instrumental in explaining the funky behaviors of the exploration.
   
   2. Diversification is key. I really tried to include a different form of plotting for each step of exploration and for each univariate, bivariate, and/or multivariate portion. I even attempted to make sure that as my plotting became more complicated, the colors became more vibrant. I used barplots, violins, facetgrids, line graphs, log scales, pairgrids, encoding plots, pinplots, etc.
   
   3. I thoroughly enjoyed incorporating `distance` into the fold. It was one of the most challenging portions of this project, and subsquently almost made me give up. I am very glad I didn't.
   
   4. Finding the perfect focus pathway. While exploring initially I wasn't entirely sure where I was going to go with this project. What I was going to explore, let alone analyze. So I think the first takeaway was learning how to let the exploration do just that, and the questions will come as they do.
      
   5. **MAIN**: I will always have more questions. No matter how much I explore. What if we represented all current gender types? Would the data be spread too thin or would we see relationships we did not think of let alone expect? What kind of marketing is the company doing that the majority of riders are subscribers, and the majority of subscribers are male identifying users in the 30-50 age range? If there was more data maybe I could find some of these things out.
   
I received a good amount of help and inspiration from Udacity's resources as well. 

[Udacity's Example Project](https://s3.amazonaws.com/video.udacity-data.com/topher/2018/August/5b7de78c_communicate-data-example-project/communicate-data-example-project.zip)

[HeatMap Help StackedOverFlow](https://stackoverflow.com/questions/55405584/heatmap-with-2-numerical-variables-and-1-categorical-variable)

[Histogram Help StackedOverFlow](https://stackoverflow.com/questions/20656663/matplotlib-pandas-error-using-histogram)


```python

```
