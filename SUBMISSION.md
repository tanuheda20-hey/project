# Hackathon submission draft — PaaniPact

## Selected problem statement
**Smart & Sustainable Future**

## Project name
**PaaniPact — fair turns for a shared pump**

## Short description
Small farming groups that share a pump need a clear way to decide who gets a watering turn and when. PaaniPact turns farmers’ stated need, waiting time, recent turn history, an expected-rain input and the group’s available pump hours into a transparent draft schedule. Members can see why each turn was suggested, adjust the inputs and review the plan together.

## What is different about this prototype?
Many irrigation tools focus on recommendations for one farm. PaaniPact explores a narrower coordination problem: **how a group can share one limited pump transparently**. The score is visible, explainable and open to community review rather than being a hidden AI decision.

## What the demo currently does
- Starts with a fictional group of five farmers.
- Ranks sample requests using stated need, time since watering, wait since last turn and a rain toggle.
- Fits sample time slots into a selected pump window.
- Shows explanations, waitlisted requests and a simple turn-history visualization.
- Lets the presenter add/remove demo members and export the schedule as CSV.

## 30-second pitch
“Several farms may depend on one shared pump, but informal turn-taking can be hard to coordinate fairly. PaaniPact creates a transparent draft schedule using the group’s stated needs, how long people have waited and the pump hours available. Members can inspect and change the plan together. Our prototype shows the scheduling flow; before real use, the rules would be validated with farmers and local agriculture experts.”

## 60-second demo sequence
1. Show the sample group and the available pump window.
2. Point to the schedule and explain that every slot has a visible reason.
3. Toggle **Rain adjustment** and show how non-urgent requests move in the queue.
4. Reduce the pump window to 4 hours and show a request move to the next planning window.
5. Add one sample farmer, then export the schedule CSV.
6. State the limitation clearly: sample data and heuristic scores only; no pump control and no agronomy claims.

## Validation plan
Before making real-world claims, speak with farmers, pump operators or an agriculture extension worker. Check whether the shared-pump problem exists in the chosen community, which allocation rules people consider fair, and how they would want to receive the schedule. Keep the prototype’s sample figures separate from any measured pilot results.

## Impact measures to test in a pilot
- Time needed to agree on a pump schedule.
- Number of missed or disputed turns.
- How evenly turns are distributed over time.
- Pump hours used versus pump hours available.
- Whether users understand and trust the reasons shown.

Do not claim water or energy savings until they are measured with suitable local data.
