<img width="850" height="551" alt="Screenshot 2025-07-19 004155" src="https://github.com/user-attachments/assets/71065f86-f359-45e7-8bfb-b35848c1555b" />
#  IPL Data Analysis Dashboard

About This Project
Welcome! I built this fully interactive dashboard because of my passion for cricket and data. I wanted to create a one-stop solution to explore the rich history of the Indian Premier League (IPL) and uncover insights from over a decade of match data. This dashboard, built entirely in Power BI, allows any user to select a season and instantly see a complete summary of winners, top performers, and overall league statistics.

📊 Key Features
🏆 Season-at-a-Glance: Select any IPL season (2008-2025) from the dropdown to see the Winner, Runner Up, and key stats for that year.

🏏 Top Performer Analysis: Instantly view the Orange Cap (most runs) and Purple Cap (most wickets) holders, complete with their stats and team information.

💥 Boundary Trackers: See which players hit the most Fours and Sixes in the selected season.

🖼️ Dynamic Visuals: Player images and team logos change dynamically based on the selected season's data.

🔢 Aggregate Statistics: View high-level stats like total matches played, centuries scored, venues used, and more.

🛠️ Technical Stack & Tools
Visualization: Microsoft Power BI

Data Source: Excel Spreadsheets

Data Transformation: Power Query (M Language)

Data Analysis: DAX (Data Analysis Expressions)

The "How-To": From Raw Data to Dashboard
This project wasn't just about dragging and dropping visuals; it involved a complete BI workflow:

Data Cleaning (Power Query): The initial data, sourced from multiple Excel files (matches.xlsx, deliveries.xlsx, players.xlsx), required significant cleaning. I used Power Query to handle missing values, correct data types, and merge tables to create a clean foundation for the model.

Data Modeling: I built a star schema data model within Power BI. The trickiest part was handling the matches table, which has two team columns (team1 and team2). I created an active relationship for team1 and an inactive relationship for team2 with my teams table. This allowed me to use DAX's USERELATIONSHIP function to correctly calculate stats for a team regardless of whether they were listed as Team 1 or Team 2.

DAX for Insights: The real magic happens with DAX! I wrote several complex measures to bring the dashboard to life. For example:

Orange Cap Winner: A measure that calculates the total runs for every batsman in a season, finds the maximum value, and returns the player's name and image.

Season Winner: A measure that filters the final match of the season and returns the winner column.

Total Matches Played: A measure that correctly counts matches for a selected team by leveraging the active and inactive relationships mentioned above.

Challenges & Learnings
Building this dashboard was a fantastic learning experience. The biggest challenge was writing optimized DAX for the top performer cards. Filtering a massive deliveries table (which has ball-by-ball data) and aggregating it efficiently taught me a lot about DAX performance. I also learned the importance of a clean data model for writing simpler and faster measures.
