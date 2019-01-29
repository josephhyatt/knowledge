# Big O Notation

Say you order Harry Potter: Complete 8-Film Collection \[Blu-ray\] from Amazon and download the same film collection online at the same time. You want to test which method is faster. The delivery takes almost a day to arrive and the download completed about 30 minutes earlier. Great! So it’s a tight race.AdvertisementWhat if I order several Blu-ray movies like The Lord of the Rings, Twilight, The Dark Knight Trilogy, etc. and download all the movies online at the same time? This time, the delivery still take a day to complete, but the online download takes 3 days to finish.

For online shopping, the number of purchased item \(input\) doesn’t affect the delivery time. The output is constant. We call this **O\(1\)**.

For online downloading, the download time is directly proportional to the movie file sizes \(input\). We call this **O\(n\)**.

From the experiments, we know that online shopping scales better than online downloading. It is very important to understand big O notation because it helps you to analyze the **scalability** and **efficiency** of algorithms.

**Note:** Big O notation represents the **worst-case scenario** of an algorithm. Let’s assume that O\(1\) and O\(n\) are the worst-case scenarios of the example above.

