# Trend-Analysis-on-TikTok

Project Capabilities:
The program was a sophisticated data analysis tool designed to mimic TikTok's "Discover" page. By processing a large JSON file containing data from thousands of TikTok posts, it could identify and rank trending content.

The program operated in two distinct modes based on a command-line argument:

1.  Trending Hashtags: When run in `hashtag` mode, the program analyzed all posts to find the top 20 most popular hashtags. The ranking was determined by a multi-level sorting logic:
    - First, by the total usage count of the hashtag.
    - Ties were broken by the total view count of all videos using that hashtag.
    - If still tied, the hashtag with the alphabetically smaller name won.

2.  Trending Sounds: When run in `sound` mode, it identifies the top 20 trending sounds. The ranking for sounds was based on:
    - The total view count of all videos that used the sound.
    - Ties were broken by the sound's unique **music ID**.

For each of the top 20 results (whether a hashtag or a sound), your program would then find and display the **top 3 most-viewed videos** associated with it, providing a snapshot of the most influential content for that trend.

Skills Gained:
This project was an exercise in handling large datasets and implementing complex ranking algorithms, strengthening several key C++ skills:

1) Advanced STL Data Structures: 
    - `std::priority_queue`: Used this container, which is perfect for efficiently finding the "Top K" elements (like the top 20 trends or top 3 videos) without needing to fully sort the entire dataset.
    - `std::unordered_map`: Used this hash map to aggregate data. For example, you could map a hashtag string to a custom object that stores its usage count, total views, and associated videos. This allows for very fast data lookup and updates.
    - `std::unordered_set`:** This was useful for tracking unique video IDs to fulfill the requirement of ignoring duplicate posts in the input file.

2) Custom Comparators: To use `std::priority_queue` or any standard sorting algorithm with the custom classes/structs (e.g., a `HashtagData` object), you had to define custom comparison logic. This is a fundamental skill for tailoring C++ standard algorithms to specific problems.

3) Complex Data Modeling: Had to design your own `struct`s or `classes` to represent and aggregate the complex information from the JSON file, such as a video's properties, a hashtag's statistics, or a sound's total views.

4) File Parsing and Data Ingestion: Gained experience reading and processing a complex, nested data format (JSON). While the instructions don't specify the method, this task required a robust way to extract specific fields from each line of the input file.

5) String Processing:** You practiced using `std::regex` (regular expressions) to parse the post's text and accurately extract all the hashtags.
