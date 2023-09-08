# Crawling_bilibili

# UP Data Collection Scripts

This repository contains a set of scripts that facilitate the collection of various types of data from UP video homepages and videos on Bilibili. The data collection is divided into several stages, including gathering homepage data, comments, barrage data (Danmaku), and automatically downloading videos.

## Prerequisites

Ensure the following tools and libraries are installed and set up:

1. Google Chrome Browser
2. Mitmproxy
3. Bilibili Helper Extension for Chrome
4. Python libraries:
   - requests
   - time
   - selenium
   - pandas
   - multiprocessing
   - lxml
   - os

## Scripts Description

### UP_Homepage

This script collects data from a UP's homepage.

#### Usage
1. Run the script.
2. Input the UP mid (found in the UP homepage URL, e.g., `1532165` in `https://space.bilibili.com/1532165/video`).
3. Input the start and end page numbers for the data collection.
4. A CSV file named `UP_Homepage.csv` will be generated, containing data useful for comment data collection.

### UP_Comments

This script collects comments data from UP's videos.

#### Usage
1. Run the script.
2. The script reads `oids` and `page` columns from `UP_Homepage.csv` to construct URLs for data endpoints.
3. A CSV file named `UP_Comments.csv` will be generated containing all collected comment data.
4. A folder named `UP_Comments` will be created, containing separate CSV files for each video's comment data.

### UP_DM

This script collects barrage data (Danmaku) from UP's videos.

#### Usage
1. Run the script.
2. Input UP mid, and the start and end page numbers for data collection.
3. Open a CMD window in the current folder and run `mitmdump -s DM_Cid-9000.py -p 9000` to start data capturing.
4. Once the capture ends (indicated by a message in the console), the data will be saved in several files similar to the UP_Comments script.

### UP_Video

This script automates the downloading of UP's videos.

#### Usage
1. Ensure Google Chrome and the Bilibili Helper extension are properly set up.
2. Run the script.
3. Input UP mid and the page number range for video downloads.
4. Videos will be downloaded to the location specified in your Chrome settings.

## Note

The collection of homepage data is crucial as it influences the collection of comment data.

## Contributing

Feel free to open issues or create pull requests to improve the scripts or documentation.

