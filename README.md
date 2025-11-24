TECHNICAL DOCUMENTATION
WEATHER-BASED FARMING SUGGESTION SYSTEM

1. INTRODUCTION
This project is a small Java program that helps farmers by giving simple farming suggestions using just two things: temperature and rainfall.
The program tells the user:
•	which crop is suitable,
•	how much irrigation is needed, and
•	if there is any weather warning (like heatwave, drought, or heavy rain).

2. HOW THE SYSTEM WORKS 
1.	The user enters temperature and rainfall.
2.	The program checks these values.
3.	Based on simple rules, it decides:
o	Which crop is best
o	How much irrigation is needed
o	Whether there is any warning
4.	It shows the results on the screen.
5.	It also saves the results into a text file so the user can view past records.

3. FEATURES OF THE SYSTEM
•	Suggests a crop based on weather
•	Gives irrigation advice
•	Shows weather warnings
•	Saves results in a text file
•	Allows the user to see old records
•	Very easy to use and understand

4. MAIN LOGIC USED IN THE PROGRAM
CROP SUGGESTION
•	High temp + low rain → Millets
•	Medium temp + good rain → Rice
•	Low temp + medium rain → Wheat
IRRIGATION LEVEL
•	Low rainfall → High irrigation
•	Medium rainfall → Moderate irrigation
•	High rainfall → Low irrigation
WARNINGS
•	Temperature > 40°C → Heatwave warning
•	Rainfall < 20mm → Drought warning
•	Rainfall > 200mm → Heavy rain warning

5. ADVANTAGES
•	Easy to understand for beginners
•	Helps students learn real-life usage of Java
•	Gives quick and simple farming suggestions
•	Works on any computer
•	No complex setup needed
•	
6. LIMITATIONS
•	Uses fixed rules
•	Not connected to real weather API
•	Limited crop options
•	No graphical interface (only console)

7. FUTURE IMPROVEMENTS
In the future, this project can be made better by adding:
•	Soil type input
•	Real-time weather API
•	More crops
•	A simple graphical UI
•	Better logic or machine learning
•	
8. CONCLUSION
This project is a simple and helpful example of how Java programming can support farming decisions. 
