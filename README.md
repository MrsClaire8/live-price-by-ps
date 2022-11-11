1. Overview
2. Tech stack
3. Function’s review


    Overview:
  The application Live-Price is designed to automate the process of calculating prices for individual products and makes it possible to keep them low. The additional function of the app is setting prices with a particular profit margin for many products at the time. The aim was to provide intuitive handling and keep GUI as simple as possible. Below is a used tech stack and a detailed description of the program’s functionality.
	

Tech stack:
  Python (version 3.9),
  SQLite3,
  Tkinter,
  Pandas,
  BeautifulSoup,
  Request,



		Function’s review:

The aim is to scrap prices of selected products from competitive online stores and set new prices in specific conditions.


    Adding new products

  The first step is to add new products to a database. We have to type the product code, name, and links to particular products in competitive online stores. We might also leave a blank row for the store which doesn’t have this product in their offer. Then the program automatically sets the default value „1000000” (which always is the highest price and therefore will not be considered). When we finish filling out the information, everything is sent to the SQLite database.

    Viewing records

  Data preview is possible by the large Listbox widget in the main app’s window. By clicking the „Wyświetl wszystko” button, records from the database show there.

    Updating selected products

  We can change pieces of information on the product’s card by clicking „Edytuj zaznaczone”

    Removing selected products

  Similarly, we can remove the selected record. These actions bring with them changes in the database.

    Searching for the product

  The program enables searching products by code. Type it in the window above the Listbox widget, and click „Wyszukaj”

    Calculating prices

  The app’s main and largest functionality is scraping and calculating the prices. By clicking „Przelicz ceny” we have to fill in the desired profit margin and search for a path to the price list file (which is a standardized file used by spawlanictwo.pl), and after that program runs. In the beginning, the app scrapes prices by BeautifulSoup and Request from provided links. The output data is saved to the database so it can be used for future analysis. Next, the scraped prices are compared to each other, and python creates a list with the lowest ones. Program gets data from the price list file (csv, we have the purchase prices of products there), compares prices back again, and sets up a new list of the lowest prices. After this, in simplification app checks a few conditions, makes calculations, and finally generates a csv file with the new prices using the Pandas library.
  
