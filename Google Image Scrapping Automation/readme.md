I used Fatkun Batch Download Image chrome extension to scrap the images. I also decided to try out the automation code with selenium provided by Codebasics to achieve the same result, but the chrome extension is easy and faster.


The code automates the process of searching for, fetching, and downloading images from Google Images based on a given search term.

### Initial Setup
- The code starts by defining a list of search terms, in this case, a single term: "Serena Williams".
- It then iterates over this list, calling the `search_and_download` function for each term.

### `search_and_download` Function
1. **Target Folder Creation**: For the given search term (e.g., "Serena Williams"), it creates a target folder where the downloaded images will be saved. The folder's name is derived from the search term, with spaces replaced by underscores.
2. **WebDriver Setup**: Initializes a Selenium WebDriver using Chrome, specified by the path to the Chrome WebDriver executable (`driver_path`). This setup now correctly uses the `Service` class to accommodate changes in Selenium's API.
3. **Fetching Image URLs**: Calls `fetch_image_urls`, passing it the search term and other parameters like the number of images to download.

### `fetch_image_urls` Function
1. **Google Images Search**: Constructs a Google Images search URL for the query and navigates to it using the WebDriver.
2. **Scrolling and Collecting URLs**: Scrolls through the search results page, simulating user interaction. It looks for image thumbnails and attempts to click on them to reveal the full-size image URLs. These URLs are collected until the specified maximum number of links to fetch is reached or there are no more images to collect.
3. **Unique URL Collection**: Uses a Python set to store unique image URLs, ensuring that no duplicate images are downloaded.

### `persist_image` Function
- For each collected image URL, `persist_image` attempts to download the image by making an HTTP GET request.
- If successful, the image content is saved to the target folder with a unique filename. The filename is generated using a SHA-1 hash of the image content to avoid naming conflicts and ensure uniqueness.
- The image is saved in JPEG format with a specified quality level.

### Conditions for Image Download
- **Maximum Number of Images**: The script continues to fetch and download images until it reaches the maximum number specified in the `search_and_download` function call (`number_images`).
- **Unique Images**: Only unique images (based on their URLs) are downloaded; duplicates are ignored.
- **Availability and Accessibility**: The image must be accessible for download (i.e., the URL must return a valid image response).

### Execution Flow
1. The script initializes the WebDriver and navigates to Google Images to perform a search.
2. It dynamically scrolls through the search results, simulating clicks to reveal full-size images, and collects their URLs.
3. Once a sufficient number of unique image URLs are collected (or the script has scrolled through all available results), it proceeds to download each image.
4. Each image is saved to the specified target directory, with care taken to handle errors in downloading or saving.

Code credit to Codebasics
