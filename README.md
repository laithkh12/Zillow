# 🏠 Zillow Property Scraper and Google Form Bot


A Python project combining **BeautifulSoup** and **Selenium** to scrape property data from Zillow and automatically populate a Google Form with the scraped details.

---

## 📋 Features

- Scrapes property details (links, addresses, and prices) from Zillow using **BeautifulSoup**.
- Automatically fills out a Google Form with the scraped data using **Selenium**.
- Saves time by automating the process of collecting and organizing rental data.

---

## ⚙️ Prerequisites

Ensure you have the following installed:

1. **Python 3.7+**
2. **Google Chrome Browser**
3. **ChromeDriver** (compatible with your Chrome version)
4. Required Python libraries:
   ```bash
   pip install beautifulsoup4 requests selenium
    ```
--- 
## 🚀 How to Use
1. Clone the Repository
2. Update the Variables
- Update the Zillow URL in the requests.get() function.
- Replace "YOUR_GOOGLE_FORM_LINK_HERE" with the link to your Google Form.
- Modify the XPATH selectors for Google Form fields if your form structure is different.
3. Run the Script
---
## 🖋️ Workflow
### 1. Scrape Property Data from Zillow
- The script sends a GET request to Zillow with headers mimicking a browser.
- It extracts:
  - Links to individual property listings.
  - Addresses of properties.
  - Prices of the listings.
- Cleans the scraped data for better readability.
### 2. Fill Google Form with Selenium
- Opens your Google Form using Chrome WebDriver.
- Enters the scraped data (address, price, link) into corresponding fields.
- Submits the form for each property.
---
## 🔧 Configuration Details
### Example Configuration:
Modify Zillow URL:
Replace "use Zillow.com" with the actual Zillow page link, e.g.:
```python
response = requests.get("https://www.zillow.com/homes/for_rent/", headers=header)
```
Update Google Form Link:
Replace the placeholder with your Google Form link:
```python
driver.get("https://docs.google.com/forms/d/e/YOUR_FORM_ID/viewform")
```
Update XPATHs:
Adapt the XPATH selectors in the script to match your Google Form fields:
```python
address = driver.find_element(By.XPATH, '//*[@id="field_xpath"]')
price = driver.find_element(By.XPATH, '//*[@id="field_xpath"]')
link = driver.find_element(By.XPATH, '//*[@id="field_xpath"]')
```
---
## ⚠️ Important Notes
- Zillow's Anti-Bot Measures:
Avoid overloading the website with requests. Use appropriate headers and consider adding delays.
- Dynamic Selectors:
Zillow and Google Forms might update their HTML structure. Be ready to update CSS Selectors or XPATHs if the script stops working.
- Rate Limits:
Running the script too often may result in temporary IP bans. Use responsibly.
---
## 🌟 Example Output
Scraped Data:
- Links:
```plaintext
['https://zillow.com/homedetails/123', 'https://zillow.com/homedetails/456']
```
- Addresses:
```plaintext
['123 Main St, New York, NY', '456 Elm St, Los Angeles, CA']
```
- Prices:
```plaintext
['$2,000', '$3,500']
```
---
## 🤝 Contributing
Contributions are welcome! Feel free to submit a pull request or suggest enhancements.
---
## 📄 License
This project is licensed under the MIT License. See the LICENSE file for details.
---
## 📖 Acknowledgments
- Zillow for providing property data (scraping must comply with their terms of service).
- Selenium and BeautifulSoup for their powerful automation capabilities.
