# PatrickCapstone

## Top 40 Fighting-game Players

## Patrick Manning Capstone Project for DDA5 at Nashville Software School

## Contents
 * Motivation
 * Data Questions
 * Know Issues and Challenges
 * Data Sources and Tools
 * Links to Dashboard and Slides

An exploration of the top 40 fighting-game players using various metrics. Who is the greatest player of all time and why?


### Motivation

Fighting-games have been a passion of mine since I was a young teenager, pumping tokens into the machines at the arcade. As the video game industry continues to grow, how are the Fighting-Game Community (FGC) and it's players keeping up? How should we define the "greatest player of all time" (GOAT)? 


### Data Questions

Who is the greatest fighting-game player? Using these metrics: total earnings, offline/online earnings, games placed, and prizes per year.
How has the pandemic affected players ability to earn a living?


### Know Issues and Challenges

Web scraping esportsearnings and cleaning and organizing the data was very challenging. I pulled 10 metrics for the years 2003-2021 and created tables and charts to visualize the data and help tell a story. 

##### web scrape and create tables for each player:
```python 3
sonicfox_url = 'https://www.esportsearnings.com/players/4603-sonicfox-dominique-mclean'
response = requests.get(sonicfox_url)
soup = BeautifulSoup(response.content, 'lxml')
tables = soup.find_all('table')
len(tables)
```
```
sonic_fox = pd.read_html(str(tables), skiprows=1)
len(sonic_fox)
```
```
sonic_fox = sonic_fox[0]
sonic_fox
```

##### added player ID column for table relationships in dashboard:
```
sonic_fox['Player ID'] = 'SonicFox'
sonic_fox
```


Gather, clean, organize and analyze data from esportsearnings.com to determine who the greatest fighting-game player of all time is. Explore the data and interesting questions or insights the data may provide. 
Create visualizations for a presentaion. Technologies used: Python, Google Slides, and PowerBI






# Top 40 Fighting Game Players Dashboard

## ***Justin Wong used as example***

![Top 40 FG Players](https://user-images.githubusercontent.com/90284913/170078383-5c55cfb9-9b28-4c40-8054-a9fa1f9794f6.png)

