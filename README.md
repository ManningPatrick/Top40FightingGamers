# Top 40 Fighting-game Players

## Patrick Manning Capstone Project for Nashville Software School DDA5

## Contents
 * Motivation
 * Data Questions
 * Know Issues and Challenges
 * Data Sources and Tools
 * Links to Dashboard and Slides

An exploration of the top 40 fighting-game players using various metrics. Who is the greatest player of all time and why?


### Motivation

Fighting-games have been a passion of mine since I was a young teenager, pumping tokens into the machines at the arcade. As the video game industry continues to grow, how are the Fighting-Game Community (FGC) and it's players keeping up? How should we define the "greatest player of all time" (GOAT)? 


##### Who is the GOAT?
![Top 40 Fighting-game players](https://user-images.githubusercontent.com/90284913/170115702-2ea13f54-fb61-4a0f-8bf2-1b5f4c640643.png)



### Data Questions

Who is the greatest fighting-game player? Using these metrics: total earnings, offline/online earnings, games placed, and prizes per year.
How has the pandemic affected players ability to earn a living?


### Know Issues and Challenges

Gather, clean, organize and analyze data from esportsearnings.com to determine who the greatest fighting-game player of all time is. Explore the data and interesting questions or insights the data may provide. Create visualizations for a presentaion.
Web scraping esportsearnings and cleaning and organizing the data was very challenging. I pulled 10 metrics for the years 2003-2021 and created tables and charts to visualize the data and help tell a story.

##### web scrape and create tables for each player:
```python 3
sonicfox_url = 'https://www.esportsearnings.com/players/4603-sonicfox-dominique-mclean'
response = requests.get(sonicfox_url)
soup = BeautifulSoup(response.content, 'lxml')
tables = soup.find_all('table')
len(tables)
```
```python 3
sonic_fox = pd.read_html(str(tables), skiprows=1)
len(sonic_fox)
```
```python 3
sonic_fox = sonic_fox[0]
sonic_fox
```

##### added player ID column for table relationships in dashboard:
```python 3
sonic_fox['Player ID'] = 'SonicFox'
sonic_fox
```

##### created 2 players tables for data visualizations:
```python 3
players_years = pd.concat([sonic_fox, punk, tokido, hungrybox, nuckledu, gachikun, armada, idom, mew2king, dragon, mena, daigo, mango, mkleo, knee, kazunoko, infiltration, fuudo, momochi, zero, sandstorm, afoxygrandpa, leffen, fujimura, itabashi, boomie, dabuz, nairo, jwong, xian, jdcr, plup, tweek, bonchan, phenom, ally, qudans, problem_x, nobi, mago])
```
```python 3
players_games = pd.concat([sonic_fox_games, punk_games, tokido_games, hungrybox_games, nuckledu_games, gachikun_games, armada_games, idom_games, mew2king_games, dragon_games, mena_games, daigo_games, mango_games, mkleo_games, knee_games, kazunoko_games, infiltration_games, fuudo_games, momochi_games, zero_games, sandstorm_games, afoxygrandpa_games, leffen_games, fujimura_games, itabashi_games, boomie_games, dabuz_games, nairo_games, jwong_games, xian_games, jdcr_games, plup_games, tweek_games, bonchan_games, phenom_games, ally_games, qudans_games, problem_x_games, nobi_games, mago_games])
```


### Data Sources and Tools

Web scraped from [esportsearnings](https://www.esportsearnings.com/players/fighting-game-players).

Technologies used: [Python](https://www.python.org/), [Google Slides](https://www.google.com/slides/about/), and [PowerBI](https://powerbi.microsoft.com/en-us/).







# Top 40 Fighting Game Players Dashboard

## ***Justin Wong used as example***
##### Filter by player name and prize earnings by year, game, and  online vs offline.
![Top 40 FG Players](https://user-images.githubusercontent.com/90284913/170078383-5c55cfb9-9b28-4c40-8054-a9fa1f9794f6.png)

