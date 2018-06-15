# Realm Royale Endpoint Feedback
**specifically related to Realm Royale**

- With the player endpoints, I'm sure other developers, and even players would love to see Class specific data (Warrior, Engineer, Assassin, Hunter, Mage) - While maintaing overall player statistics. This could include typical 'getPlayerStats' information, but possibly under a new endpoint such as 'getPlayerClassStats{playerID | playerName, classID | className}' to not slow query performance for 'getPlayerStats' endpoint.

- For the basic 'getPlayer' API Endpoint, I'd love to see a field for SteamID if they made an account through Steam, and if not it could just be set to null. This would be very relevant for developers who are making Data Visualization projects based off of Realm Royale statistics, and a consumer using the service could lay claim to a certain user by authenticating via Steam - To be confirmed by the SteamID field in the getPlayer query.

- If class specific data is ever implemented to a player data endpoint I think it would be beneficial for those doing statistical analysis to see total value of 'X' effect each ability that class has. 

- The 'average_placement' and 'placements' being TBD due to query performance is understandable. Perhaps you could just track placement count for top 5 or top 10, and calculate 'average_placement' after every game instead of keeping track of it via the 'placements' field (Which I assume is what would be done if it is said to be detrimental to query performance). 

  What could be done is assigning each placement a static value or a score. '1st place: 1 point, 2nd place: 2 points, 3rd place: 3 points`, and after every game add the placement value of that match to a 'total_placement' field in player stats then divide that by 'games_played' to get the average placement. This would rid the need to track each individual placement by only tracking the one single value, thus reducing risk for query performance issues.  
  
  Sadly this would take away some specific information that may be wanted by developers, but would still allow an `average_placement` field that would be accurate up to the Players first match (Which is what I would personally prefer rather than only for the past 30 days). Could also be used to save Engineers valuable time from being forced to work on a method to optimize the query performance!