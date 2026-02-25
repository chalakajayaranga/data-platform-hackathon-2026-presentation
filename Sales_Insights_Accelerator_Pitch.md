Slide - 1
Product Name: Snow Mind
Challenge : Conversational Revenue Intelligence
Team : Pagero Hackstreet Boys

Data Platform Hackathon 2026


Slide - 2

Challenge

Transform how Reuters analysts work with RUM (Reuters Unified Marketplace)'s enhanced data ecosystem by building an intelligent semantic layer on Snowflake that removes traditional query barriers. Create a natural-language interface that lets analysts explore visual content performance, trends, and user engagement patterns through conversational questions—without needing complex SQL.


Slide - 3
Approach - 1
Using snowflake AI Agent

Generated a semantic view for the data tables and created an AI Agent. So the users can 


_____________           ______________________________________________       
| AI Agent Chat | ------> | Convert NLP query to Snowflake SQL (Cortex Analyst) | ------>  
—------------------            —-------------------------------------------------------------------------
__________________________________            _____________________
| Summarize response (Cortex Complete) | ------> | Visualize response (AI Agent) | 
—------------------------------------------------------           —---------------------------------  


Drawbacks​
Semantic model have to be updated manually if the database structure changed ​
Less control on visualization​ the response

Slide - 4

<Screen Shot of Ai Agent: images/ai-agent.png>

Slide - 5
Approach -2 
Developed a Custom Chat Application using Streamlit

_____________           ______________________________________________       
| Streamlit Chat | ------> | Convert NLP query to Snowflake SQL (Cortex Analyst) | ------>  
—------------------            —-------------------------------------------------------------------------
__________________________________            _____________________
| Summarize response (Cortex Complete) | ------> | Plot response (Ploty) | 
—------------------------------------------------------           —---------------------------------

Slide - 6

Why Streamlit approach?
Full control on chat UI
Showing visual diagrams inside the chat UI seamlessly
Ability to export queried data as csv
Ability to enhance semantic views for any new schemas with relationships
Maintain chat history
Navigate between chats & continue

By using Ploty:
No need for moving to external visualization tools like PowerBI
No more expert knowledge
No extra cost


Slide - 7

Streamlit App in Action - Chat Option
Chat flow mmd

flowchart TD
    Start([User Opens App]) --> Config{Configuration<br/>Complete?}
    Config -->|No| SelectConfig[Select Database,<br/>Schema & Semantic View]
    SelectConfig --> Config
    Config -->|Yes| EnterQuery[User Enters<br/>Natural Language Query]
    
    EnterQuery --> Analyst[Cortex Analyst:<br/>Convert to SQL]
    Analyst --> ExecSQL[Execute SQL<br/>on Snowflake]
    ExecSQL --> GetResults[Get Query Results]
    
    GetResults --> GenAnswer[AI Generates<br/>Streaming Answer]
    GenAnswer --> CheckViz{Need<br/>Visualizations?}
    
    CheckViz -->|Yes| AnalyzeData[Analyze DataFrame<br/>Schema]
    AnalyzeData --> GenCharts[AI Suggests<br/>Chart Definitions]
    GenCharts --> ValidateCode[Validate Chart<br/>Code Security]
    ValidateCode --> RenderCharts[Render Plotly<br/>Charts]
    RenderCharts --> Display
    
    CheckViz -->|No| Display[Display Answer<br/>to User]
    Display --> NextQuery{More<br/>Questions?}
    NextQuery -->|Yes| EnterQuery
    NextQuery -->|No| End([End])

    style Start fill:#e3f2fd
    style End fill:#e3f2fd
    style Config fill:#fff3e0
    style Analyst fill:#f3e5f5
    style GenAnswer fill:#f3e5f5
    style GenCharts fill:#f3e5f5
    style Display fill:#e8f5e9


Slide - 8

Streamlit App in Action - Settings Option

Settings flow mmd

flowchart TD
    Start([Settings Tab]) --> SelectDB[Select Database<br/>& Schema]
    SelectDB --> GenBasic[Generate Basic<br/>Semantic View<br/>from Cortex Analytics and Upload]
    GenBasic --> GetTables[Retrieve Table<br/>Metadata]
    GetTables --> Enhance[AI Enhances<br/>Semantic View<br/>with Descriptions]
    Enhance --> SaveYAML[Save enhanced YAML<br/>to Snowflake Stage]
    SaveYAML --> End([Ready for Use])

    style Start fill:#e3f2fd
    style GenBasic fill:#f3e5f5
    style Enhance fill:#f3e5f5
    style End fill:#e8f5e9

Slide - 9

Live Demo

Slide - 10
Business Impact

Slide - 11
Future works
Add dynamic tables along with indexes for improve the performance
Call openarena chains from streamlit app instead of using Cortext to integrate with powerful LLMs
Integrated with Power BI to visualize the data in Power BI

Slide - 12
Challenges faced
Our team members only had free license in PowerBi.Therefore couldn't able to integrate our streamlit app with PowerBi
Since outside traffic is blocked in the app running on snowflake couldnt able to integrate with openareana chains.

Slide - 13
Lessons Learned

Slide - 14

Thank You! 