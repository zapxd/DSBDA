### Viva Questions on Web Scraping and Review Scraper Implementation

---

**1. What is web scraping? Explain the process involved.**

**Answer:**
Web scraping is the process of extracting large amounts of data from websites automatically. The scraped data is often unstructured and is then structured in a format like a spreadsheet or a database for further analysis. The process involves two key parts:
- **Crawler**: An AI algorithm that navigates through websites by following links to find the data required.
- **Scraper**: A tool that extracts the specific data from the website, typically after the crawler collects it.

---

**2. What is the purpose of web scraping in data analysis?**

**Answer:**
Web scraping is used to collect data from websites that is often not available in structured formats like databases or APIs. It is particularly useful when data needs to be extracted from web pages for analysis, such as customer reviews, product information, pricing, and more. Once scraped, the data can be used for market analysis, sentiment analysis, trend analysis, etc.

---

**3. What Python libraries are used for web scraping and why?**

**Answer:**
Two widely used libraries in Python for web scraping are:
- **BeautifulSoup**: It is used to parse HTML and XML documents. It creates a parse tree to extract data from the HTML tags. It is useful for navigating, searching, and modifying the parse tree.
- **Requests**: It is used to send HTTP requests to fetch content from a web page.
These libraries make it easy to extract and manipulate web data.

---

**4. What is the role of the `requests` library in web scraping?**

**Answer:**
The `requests` library in Python is used to send HTTP requests to web servers to retrieve content from a webpage. It handles HTTP protocols like GET, POST, etc. It simplifies the process of interacting with websites and allows users to easily fetch HTML content which can then be parsed for specific data using other libraries like BeautifulSoup.

---

**5. What does `BeautifulSoup` do in web scraping?**

**Answer:**
BeautifulSoup is a Python library used to parse HTML and XML documents. It creates a parse tree for parsing HTML documents, making it easy to extract data from HTML tags. It supports methods for navigating the document tree, searching for elements, and modifying the document's structure if necessary.

---

**6. How does a typical web scraper fetch customer reviews, ratings, and product details from an ecommerce website?**

**Answer:**
To fetch customer reviews, ratings, and product details from an e-commerce website, a web scraper:
1. **Sends an HTTP request** to the product page using `requests`.
2. **Fetches the HTML content** of the page.
3. **Parses the HTML content** using `BeautifulSoup` to find specific tags that contain the required information (e.g., customer name, review text, ratings).
4. **Extracts the necessary data** from the tags.
5. **Stores the extracted data** in a structured format like a CSV file or a database for further analysis.

---

**7. In the sample code provided, what is the purpose of `gethtml` function?**

**Answer:**
The `gethtml` function sends an HTTP request to the given URL using the `getdata` function, retrieves the HTML content of the page, and parses it using BeautifulSoup. It returns a BeautifulSoup object which represents the page's structure and is ready for further parsing to extract the desired data.

---

**8. How does the scraper in the sample code fetch the customer names from the Amazon product page?**

**Answer:**
The scraper finds the customer names by using the `find_all` method of BeautifulSoup to locate the `<span>` HTML tags with the class `a-profile-name`, which contain the customer names. It then loops through these tags, extracts the text (i.e., the customer names), and stores them in a list.

---

**9. What kind of data can you extract from an e-commerce site using web scraping?**

**Answer:**
From an e-commerce website, you can scrape data such as:
- Product details (name, price, description)
- Customer reviews and ratings
- Product images and specifications
- Shipping details and availability
- Seller information
- Discounts and offers

---

**10. What are the ethical considerations when performing web scraping?**

**Answer:**
- **Respect the website's `robots.txt` file**: This file specifies which pages can or cannot be scraped.
- **Avoid excessive load on the website**: Make sure that the frequency of scraping does not overload the website’s servers.
- **Data privacy**: Do not scrape personal or sensitive information that violates user privacy.
- **Compliance with legal regulations**: Ensure compliance with laws such as GDPR, which protects user data.

---

**11. What is the purpose of using `select` method in BeautifulSoup, and how is it different from `find_all`?**

**Answer:**
The `select` method in BeautifulSoup is used to find elements using CSS selectors. It allows more flexibility and precision when targeting elements, as it can select elements based on their CSS class, ID, tag name, etc. The `find_all` method, on the other hand, is used to find all instances of a specific tag or element but without the ability to use complex selectors. `select` is more powerful for advanced queries.

---

**12. Explain how the `pandas` library is used in web scraping to store data.**

**Answer:**
The `pandas` library is used in web scraping to structure and store the extracted data in a DataFrame, which is a 2D table-like structure with labeled rows and columns. It makes it easy to manipulate, filter, and analyze the scraped data. For example, in the sample code, `pandas.DataFrame.from_dict()` is used to convert the extracted data into a DataFrame, allowing for efficient data manipulation and export to formats like CSV or Excel.

---

**13. What challenges might you face while web scraping an e-commerce website?**

**Answer:**
Challenges include:
- **Dynamic content**: Some websites load content via JavaScript, which may not be available in the initial HTML response. In such cases, you may need to use tools like Selenium or Playwright to interact with the page.
- **Anti-scraping measures**: Websites may block or limit access to scrapers by detecting unusual traffic patterns or requiring CAPTCHAs.
- **HTML structure changes**: If the website changes its HTML structure, the scraper may break and need to be updated.
- **Legal issues**: Some websites prohibit scraping in their terms of service, so legal compliance should always be checked.

---

**14. What is the advantage of using `requests.get()` in web scraping?**

**Answer:**
`requests.get()` is a simple and efficient way to send an HTTP GET request to retrieve content from a web page. It handles the complexities of making requests, managing headers, and processing responses. It is lightweight and easy to use compared to other alternatives.

---

**15. What is the difference between a crawler and a scraper in the context of web scraping?**

**Answer:**
- **Crawler**: A program that browses the web and follows links from one page to another to discover new URLs. It collects the links to gather the data.
- **Scraper**: A tool that specifically extracts data from the HTML content of the page(s) collected by the crawler. It extracts the required information (e.g., product name, reviews, ratings).

---

**16. What is the significance of the `User-Agent` header in web scraping?**

**Answer:**
The `User-Agent` header in web scraping is used to simulate a request from a real web browser. Some websites block requests that do not have a proper `User-Agent`, assuming they are from bots or scrapers. By setting this header, you can mimic a legitimate user request, which can help bypass such blocks.

---
