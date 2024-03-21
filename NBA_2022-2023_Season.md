## 2022-2023 NBA Season Stats

<img src="images/NBAC.png?raw=true"/>

Have you ever had a conversation with someone who is a die hard sports fan? I am talking about that type of person whose seasons revolve around baseball, basketball, football, and hockey not spring, summer, fall, and winter. I am always surrounded by sports fanatics so I took this opportunity to understand the NBA more in depth and provide some data driven insights. 

### Major Findings

- Nikola Jokic and Domantas Sabonis outperformed many point guards regarding their total number of assists.
- Joel Embiid was the MVP for the 2022-2023 season with an average of 33.1 points, 10.2 rebounds, and 4.2 assists per game.
- Jayson Tatum led the league in total points scored, playing a total of 74 games during the season.
- LeBron James and Giannis Antetokounmpo are very similar performing players.
- The Centers led many teams in 3 point percentages.
  
### The Data

For this project, I used the 2022-2023 Player Stats: Totals dataset from [Basketball-Reference](https://www.basketball-reference.com/leagues/NBA_2023_totals.html)

There was a total of 539 players, but with all the trades made this season, there were 680 rows. There were 32 columns which included stats such as shooting percentage for different shots, rebounds, assists, and turnovers and other informatin such as rank, team, and position. I used **Tableau** to create visualizations and a story to share my findings. The color scheme used is to differentiate the positions that the players are on each team. Dark blue = Centers, Orange = Power Forwards, Light Grey = Point Guards, Dark Grey = Small Forwards, and Light Blue = Shooting Guards. 

<img src="images/Legend.png?raw=true"/>


### Analysis

### Dominating Centers

In order to organize the data for assists per player, per position, I used a Treemap. This allowed me to show hierarchical data as a set of nested rectangles. The largest rectangle represents the point guards, as they typically have the most assists. I also restricted the data to only show players who had at least 200 assists. While the smallest rectangle is composed of the centers, it is important to note that the leading centers, **Jokic and Sabonis, have assist stats as high as some of the leading point guards**. As a center, typically you are "fed the ball" to score in the paint. However, in an interview with Jokic, he explains the differences between European and American basketball. The size of the court, the lines, and some rules are different. Having started playing basketball in Europe, Jokic and Sabonis may have a different style of play that allows them to thrive more in the NBA.

<img src="images/Assists.png?raw=true"/>

### 2022-2023 League MVP

Using this bubble scatter plot, the X and Y axes represent average points per game and average assists per games, respectively. The size of the bubble correlates with the average number of rebounds per game. 

Embiid put up on average, 33.1 points per game, 4.2 assists, and 10.2 rebounds. While he doesn't lead the centers with the most assists, he comes in second place for top scorer in the NBA with 2183 points. The only other 3 players to score over 2,000 points during the season were point guards and small forwards. 

**Embiid was the MVP**. There is some controversy with Denver fans as to why Jokic didn't receive the MVP. Embiid played 66 games while Jokic played 69. A three game difference likely wouldn't affect the average stats very much. While Embiid led his team to the NBA playoffs, and played fantastic, they lost to the Celtics in the conference semifinals. Jokic led his team all the way to the finals and won. However, Embiid secured the title of MVP with 73 votes. Runners up were Nikola Jokic with 15 votes and Giannis Antetokounmpo with 12.

<img src="images/BubbleA.png?raw=true"/>

### Leading Scorer

Looking at the stacked barchart for leading scorers, we see that Jayson Tatum scored the most for the Celtics. I restricted the data on this chart to only show players who scored at least 500 points during the regular season.

<img src="images/Lscorers.png?raw=true"/>

Also, seen in the bubble scatter plot for total stats, **Tatum is the leading scorer in the whole league with 2225 points**. I was curious as to why his ranking for leading scorer dropped so much when the average was taken into consideration. I looked at the raw data and the maximum number of games played was 83 (a traded player as the NBA has 82 regular season games) and the minumum was 1 game. Tatum played 74 games. While this is beneficial to the Celtics, it actually reduced his average points per game compared to other players like Joel Embiid and Luka Doncic who only played 66 games during the season. Reasons such as load management and injuries often reduce player's total games played. 

<img src="images/BubbleT.png?raw=true"/>

### The Goat vs The Greek Freak

LeBron James is often referred to as "The Goat", however, I do not agree. Michael Jordan will forever be The Goat, but that is not part of this analysis. It is apparent in this data that both James and Antetokounmpo are highly performing power forwards. Considering secondary positions, James would be a point guard and Antetokounmpo would be a center. **Antetokounmpo outscores and outrebounds James, but James has more assists per game**. They are both fairly similar in size, Antetokounmpo is 6'11", 243 lbs, with a 7'3" wingspand and James is 6'9", 250 lbs, with a 7'0" wingspang. James is also 39 years old and has spent 21 years in the league while Antetokounmpo is on his 11th year in the league at the age of 29. The question is, will Antetokounmpo be on the same level of play in 10 years? We will have to wait and see. 

<img src="images/Bubble.png?raw=true"/>

### Basketball Becoming Less Positional

I recently read an article about the NBA going offically position-less in the 2024-2025 NBA season. This is big news. Over the last decade, the game has changed so much. Portrayed in this 3 point percentage heatmap, it is evident that **centers are dominating and leading the following teams in 3 pointers: Atlanta Hawks, Boston Celtics, Brooklyn Nets, Houston Rockets, Utah Jazz, Washington Wizards, and Oklahoma City Thunder (centers tied with their shooting guards)**. Players like Al Horford on the Celtics shooting 44.6% from the 3-point line and Kristaps Porzingis on the Washington Wizards with 38.5%, exemplify how centers are no longer stuck in the paint. Gone is the day where point guards and shooting guards dominate the scoreboard. 

<img src="images/3pt.png?raw=true"/>

### Changing The Game

This [Forbes article](https://www.forbes.com/sites/bryantoporek/2024/02/29/how-the-nbas-65-game-rule-for-awards-impacts-players-contract-bonuses/?sh=6807625534e3) discusses all the changes that will go into effect next season. One crucial change is that players have to play 20 minutes in at least 63 games and 15-20 minutes in two games in order to be eligible for most awards. These new rules will be hard-hitting for players who face injuries during the season. The reigning MVP, Embiid, would not be eligible for MVP for the 2023-2024 season due to the number of games he has missed for his meniscus injury. 

As seen in the analysis, the top perfoming centers like Jokic and Sabonis have developed into more well-rounded players as they dominate in passing as well as shooting. It will be interesting to see how the position-less game affects players like James and Antetokounmpo who play at almost an equal level as well as players like Tatum and Embiid who led the league in scoring. To see all these visualizations to find your own insights check out my [Tableau Story](https://public.tableau.com/views/2022-2023NBA/AnalysisofNBA22-23Season?:language=en-US&publish=yes&:sid=&:display_count=n&:origin=viz_share_link).

### Traditions That Remain
Come March every year, the atmosphere around basketball always becomes more exciting. This increased interest in the sport is usually fueled by the NCAA March Madness tournament. While completing this project, I found myself spending every night after work tuning into an NBA game. I hope this project inspires you to catch a game or even get involved in March Madness at the collegiate level and make a bracket!
