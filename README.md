# SupportTicketPerformanceAnalysis

Title: Dynamic Support Ticket Performance Dashboard

## Project Overview:

An interactive Google Sheets dashboard to monitor support ticket trends, agent productivity, regional load, and SLA compliance.

## Objective:

- Visualize agent performance  
- Identify top ticket-generating regions  
- Track SLA compliance  
- Monitor resolution time trends  

## Tech Stack:

- Google Sheets  
- Pivot Tables  
- Charts  
- Advanced Formulas  
- Conditional Formatting  

## Dashboard Preview:
![Dashboard Preview](docs/dashboard_preview.png)

## Live Dashboard:
 [View Interactive Dashboard](SupportTicketDataAnalysis)

## Data & Methodology:

**Dataset:**  
- 800 customer service ticket records  

**Columns Used:**  
- Ticket_ID  
- Date  
- Issue_Type  
- Priority  
- Status  
- Resolution_Time_Hours  
- Agent  
- Customer_Region  


## Analysis Steps:

- Cleaned data to remove duplicates  
- Created resolution time buckets  
- Calculated SLA status (Met / Delayed)  
- Built pivot tables for aggregation  
- Designed interactive dashboard for insights  


## Key Formulas:

SLA Status

=IF(F2>8,"Delayed","Met TAT")
(8 hours considered as TAT)
Resolution Buckets
=IFS(F2<=4,"0-4 hours",
     AND(F2>4,F2<=8),"4-8 hours",
     AND(F2>8,F2<=12),"8-12 hours",
     F2>12,"Beyond 12 hours")

Resolved Tickets Count
=COUNTIF(E2:E801,"=Resolved")

Average Resolution Time
=AVERAGE(F2:F801)


## Dashboard Components:

Pivot Tables
Interactive Charts
KPI Cards
Slicers/Filters
Conditional Formatting:
🔴 Red → SLA NOT MET
🟢 Green → SLA MET


##  Pivot Analysis
Pivot 1: Ticket Status by Agent
 Insight:
- Agent C handled the highest ticket volume.  
- Majority of tickets are in **Resolved** status.  
- Open tickets (165) contribute to backlog.

Pivot 2:  Issue Type Distribution by Agent
Insight:
- **Payment Failure (113)** is the top ticket driver.  
- Authentication issues **(Login + Password)** form a significant share.  
- Agent workload appears relatively distributed but with variation in specialization.

Pivot 3: Regional Load by Agent
Insight:  
- **North America (214)** generates the highest ticket volume.  
- South America is a close second.  
- Load is fairly balanced globally but slightly heavier in the Americas.

Pivot 4:Count of Tickets by Issue Type (Total = 800)
Insight:
- Distribution is very balanced.
-Highest volume: Payment Failure (117).
- Lowest volume: Bug Report (89).
- Difference between highest and lowest is small (28 tickets).

Pivot 5: Resolution Bucket by Region:
Insights:
- Majority of tickets fall in 5–12 hours.
-Very few tickets resolved within 0–4 hours.
-Significant number exceed 12 hours.

Regional Breakdown:
APAC (167 Total)
0–4 hrs: 4
5–12 hrs: 25
Beyond 12 hrs: 27
EMEA (177 Total)
0–4 hrs: 4
5–12 hrs: 23
Beyond 12 hrs: 27
North America (214 Total)
0–4 hrs: 10
5–12 hrs: 29
Beyond 12 hrs: 27
South America (212 Total)
0–4 hrs: 5
5–12 hrs: 30
Beyond 12 hrs: 28

Pivot 6: Customer Region Distribution:
Insight: 
-Americas combined account for ~53% of tickets.
-Distribution is relatively even globally.
-No single region dominates significantly.

Pivot 7: SLA Status by Issue Type
Observations:
All issue types have significantly higher Not Met vs Met counts.
SLA compliance is consistently low across categories.
No single issue type shows strong SLA performance advantage.
Pattern:
High-volume categories (Payment Failure, Password Reset, Access Request) also show high SLA breaches.
Even lower-volume categories (Bug Report, Performance Issue) follow similar SLA patterns.
Pivot Insight:
SLA underperformance is systemic, not issue-specific.

Pivot 8:SLA Status by Region
Observations:
All regions show more Not Met than Met.
North America and South America have slightly higher total ticket volumes.
SLA performance pattern is consistent across all regions.
Pattern:
No region significantly outperforms others in SLA compliance.
SLA gap is uniform globally.
Pivot Insight:
SLA issue is global, not regional.

Pivot 9: Issue Type vs Region
Observations:
Ticket distribution across regions is fairly balanced.
Americas (North & South) show slightly higher counts per issue type.
No issue type is concentrated in a single region.
Pattern:
Payment Failure, Password Reset, and Access Request remain high across all regions.
System Crash and Performance Issues are evenly distributed.
Pivot Insight:
Demand pattern is globally consistent; no region-specific issue spike.

## Key Performance Insights

Ticket Volume & Closure
Total Tickets: 800
Closed Tickets: 562
Closure Rate: ~70%
~30% backlog remains and needs attention

SLA Performance (Major Risk)
SLA Breach: 82.38%
-Indicates significant process inefficiency.
-Possible Causes
  --Resolution delays
  --Prioritization gaps
  --Resource constraints

Action: Immediate SLA review and workload balancing recommended.

## Resolution Time Trends

Average Resolution Time: 19.05 hours
Highest Resolution Time
Login Issues (~21 hrs)
Password Reset (~20 hrs)

Insights:
Simpler issues resolved faster
Authentication issues are the biggest time drain.

 ## Agent Performance: 
 
Top Performer: Agent C (~175 tickets)
Strong Performers: Agent D, Agent B
Lowest Volume: Agent E (~135 tickets)

Insights
Possible workload imbalance
Skill variation across agents
Queue allocation inefficiency

Recommendation: Rebalance workload and upskill lower performers.

## Regional Distribution:

North America: ~26.8% (highest)
South America: ~26.5%
APAC: ~24.6%
EMEA: ~22.1% (lowest)

 North America slightly drives higher load

 
# Executive Summary
The dashboard shows a healthy closure rate (~70%) but a critical SLA breach level (82%), highlighting process inefficiencies. Authentication-related issues drive the highest resolution times, and agent workload distribution indicates opportunities for performance optimization.

# Recommendations
Implement SLA alert system
Deep dive into login/password workflows
Rebalance agent workload
Introduce priority-based routing









