Fantasy Formula 1 Project, Software Engineering @Unibo

***

# Fantasy Formula 1 - F²1 

## Project Description
The Formula 1 (F1) World Championship is a yearly motor racing competition held on various circuits across the globe. **Fanta Formula 1 (F²1)** is a Fantasy Game that allows users to create their own team of drivers and join a league to compete against other players. At the end of every real race, the application calculates scores based on the drivers' performances, assigning bonuses and maluses.

## Main Features
* **Team Composition:** A team is made up of 3 Drivers, 1 Constructor, and 1 Legend.
* **Budget Management:** The game's internal currency is the "Wheel". Users have a maximum budget of 100 Wheels to build their Team.
* **The Legends:** A unique feature of the game is the ability to choose a "Legend" (a past F1 champion) as a team member. Each legend has a unique special ability that adds extra points to the Team's score.
* **League Competition:** Users can compete by creating a League or joining an existing one using a unique identification code. Upon creation, teams are also automatically enrolled in a Global leaderboard.
* **Multi-team Management:** Each user has the possibility to create up to 5 active teams.

## Roles and Privileges
* **User (Utente):** Can register, create teams, join leagues via a unique code, and view the game rules and leaderboards.
* **League Manager (GestoreLega):** A user who creates a League assumes management privileges over it. They can assign a name to the league, set a maximum number of participants, expel unwanted users, and delete the league.
* **Administrator (Amministratore):** Designated accounts managed directly within the system53]. They are responsible for registering and updating data for constructors, drivers, and legends29]. After each Grand Prix, they enter the drivers' results along with any bonuses or maluses to update the leaderboards.

## Architecture and Technologies
* **3-Tier Architecture:** The system uses a three-tier client/server architecture consisting of a database, application server, and client. 
* **Design Patterns:** The architecture employs the **Broker** pattern to manage sessions, providing an extra layer of abstraction and decoupling clients from servers. The **State** pattern is used to model the dynamic privileges of a user when they become a League Manager. The **Flyweight** pattern optimizes memory management for Components (Drivers, Constructors, Legends) by separating intrinsic and extrinsic states.
* **Modularity:** Different servers handle distinct functionalities: separate servers for Administrator tasks, User/League Manager tasks, Login, Registration, and Logs.
* **Deployment:** The web application and its components are deployed using `.war` (Web Application Archives) files.

## Security
* **Encryption:** To guarantee security, communications between the client and server use the TLS protocol (HTTPS).
* **Isolated Persistence:** To avoid a single point of failure and maintain integrity, Application Data (DBMS) and Logs are kept on two separate servers.
* **Tracking and Access Control:** The system logs all actions and exchanged messages to trace operations176, 177, 178]. Administrators analyze these logs to identify atypical access patterns or discrepancies. The system also implements access control policies, such as blocking access after a certain number of failed attempts.

## Implementation
* The provided implementation is just a functioning protoype that demonstrates the basic functions of the web application. Obviously, the project can be optimized.
