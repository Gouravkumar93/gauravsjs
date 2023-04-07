# gauravsjs
Phyton for Data IBM Assignment

#Question 1: Use yfinance to Extract Stock Data
tesla= yf.Ticker("TSLA")
tesla_data= tesla.history(period= "max")
tesla_data.reset_index(inplace=True)

#Question 2: Use Webscraping to Extract Tesla Revenue Data
gme_data.reset_index(inplace=True)
url= " https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-PY0220EN-SkillsNetwork/labs/project/revenue.htm "
html_data = request.get(url).text
soup= beautiful_soup(html_data,'html5lib')
tesla_revenue = pd.Dataframe(columns={"Data", "Revenue"})
tesla_revenue["Revenue"] = tesla_revenue['Revenue'].str.replace(',|\$',"")
tesla_revenue.dropna(inplace=True)
tesla_revenue = tesla_revenue[tesla_revenue['Revenue'] != ""]
tesla_revenue.tail()


#Question 3: Use yfinance to Extract Stock Data

GameStop= yf.Ticker("GME")
gme_data= GameStop.history(period= "max")
gme_data.reset_index(inplace=True)


#Question 4: Use Webscraping to Extract GME Revenue Data
url =" https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-PY0220EN-SkillsNetwork/labs/project/stock.html."
html_data= requests.get(url).text
soup= beautiful_soup(html_data, 'html5lib')
gme_revenue.tail()

Question 5: Plot Tesla Stock Graph
import matplotlib.pyplot as plt


tesla_data = tesla_data[:datetime.date(2021, 6, 30)]
tesla_revenue = tesla_revenue[:datetime.date(2021, 6, 30)]


plt.plot(tesla_data, label='Tesla Stock Data')
plt.plot(tesla_revenue, label='Tesla Revenue Data')


plt.title('Tesla Stock Data and Revenue Data')
plt.xlabel('Date')
plt.ylabel('USD')


plt.legend()


plt.show()


Question 6: Plot GameStop Stock Graph
import matplotlib.pyplot as plt

# Assuming gme_data and gme_revenue are arrays or lists containing the corresponding data.

# Selecting only the data up to June 2021.
gme_data = gme_data[:datetime.date(2021, 6, 30)]
gme_revenue = gme_revenue[:datetime.date(2021, 6, 30)]

# Plotting the data.
plt.plot(gme_data, label='GameStop Stock Data')
plt.plot(gme_revenue, label='GameStop Revenue Data')

# Adding a title, x-axis label, and y-axis label.
plt.title('GameStop Stock Data and Revenue Data')
plt.xlabel('Date')
plt.ylabel('USD')

# Adding a legend.
plt.legend()

# Displaying the graph.
plt.show()
