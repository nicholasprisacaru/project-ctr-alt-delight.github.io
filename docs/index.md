## Who We Are

1. Samuel
2. Nicholas
3. Aishik
4. Zaid


## What's Our Project?

#### API:
- Tiingo API

### Justification: 

| Factors                                 | Tiingo                            | AlphaVantage                  | Choice |
|-----------------------------------------|-----------------------------------|--------------------------------|--------|
| Request Limit (Per Day)                 | 1000                              | 25                             | Tiingo |
| Data                                    | More Comprehensive                | Less Comprehensive             | Tiingo |
| Connections                             | IEX Exchange                      | Nil                            | Tiingo |
| Real-Time Data Availability             | Available for All Instruments     | Limited for Certain Instruments | Tiingo |
| Extensiveness of Data                   | Extensive for All Instruments     | Extensiveness Depends on Specific Instrument & Timeframe | Tiingo |
| Niche Data                              | May Be Unavailable                | May Be Unavailable             | Tie    |
| Documentation & Developer Support       | Comprehensive                     | Comprehensive                  | Tie    |

**Conclusion**: Since Tiingo beat AlphaVantage for all 3 aspects, we decided to choose Tiingo

#### Endpoints: 
- IEX(Investors Exchange)
- EOD(End-Of-Day) Stock Price

#### Requirements: 
- Authentication Credentials

#### Constraints: 
- 50 Requests/Hour
- 1000 Requests/Day

#### Research Question:
- How have the different industries on the financial markets performed over the last 5 years?

#### Potential Industries to analyse (Best performing Sectors according to [Bloomberg UK](<https://www.bloomberg.com/markets/sectors>))
- Information Technology
- Financials
- Healthcare
- Defense
- Real Estate
- Industrials
- Communications
- Consumer Staples
- Consumer Discretionary
- Energy
#### How We'll Get There:

| Steps | Execution                                                                 |
|-------|---------------------------------------------------------------------------|
| 1     | Sign-up with Tiingo API to get credentials                                |
| 2     | Use credentials to receive authentication token                          |
| 3     | Make API requests and receive raw JSONL responses                         |
| 4     | Normalize responses to 3rd Normal Form (3NF) and select desired fields    |
| 5     | Store in SQLite database                                                 |
| 6     | Read database and use plotting libraries (Matplotlib, Let's-plot) to make visualisation |


![Project Flowchart](project_flowchart.png)

#### Work Distribution:

| Name                | Role                                                                 |
|---------------------|----------------------------------------------------------------------|
| Samuel              | Data Collection -> Gather credentials and access token to query Tiingo API for JSONL responses |
| Nicholas & Aishik   | Data Manipulation -> Use Pandas to create normalized DataFrames and save them to a SQLite database |
| Zaid                | Data Visualisation -> Use refined data to plot and visualise data    |



#### Constraints:
1. Limited API Requests -> Will Structure Requests To Maximise Use 
    
2. Multiple Endpoints Increase Complexity And Processing Times -> Reduce Data Redundancy 
    
3. Have Never Used Tiingo, May Be Difficult To Utilize -> Practice Over Break, Alternative API (AlphaVantage)
    
4. Free version of Tiingo API only allows **50 requests per hour** and **1000 requests per day**
    
5. Tiingo API only has 5 years worth of historical data, making it hard to extrapolate long-term trends 
        
6. Due to the excessive volumne of data we have to collect, we foresee an issue regarding the upper threshold of git commits for databases (100mb) for our SQL database, so we would must remember to use gitLFS
    
7. Loading time could potentially take a long time due to the sheer volume of data we would collect
    

#### Risk Mitigation & Back-Up Plans
1. Exceeding Data Request Limit: We May Exceed The 50 Limit Per Hour Requests Limit
    -Optimize API calls by bundling multiple queries into a single request when supported

2. Data Accuracy: Data Provided May Be Inaccurate Or Outdated Due To Errors in Tiingo's Sources Or Delays
       -Double-check data With Other Sources Like Yahoo Finance

3. API Downtime/Outages: The API may go down for maintenance/improvements
       -Use An Exponential Back-Off Strategy Where We Retry At Increasing Time Intervals


## Project Planning & Research Design

![Project Timeline](project_timeline.png)

