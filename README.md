## Overview

Overview
ChromeRadio is a browser extension designed to enhance your online audio experience. The extension scans web pages for audio links, specifically targeting MP3 and OGG files, and lists them for easy access and management. It offers features such as saving links to a local library and providing a search functionality to quickly find your favorite audio content.

##
## Features

Features
- **Audio Link Detection**: Automatically scans web pages for audio links (MP3/OGG) and lists them.
- **Library Management**: Save audio links to a local library for easy access.
- **Search Functionality**: Search through the saved library with a simple keyword search.
- **Popup Interaction**: Toggle display options between showing URLs and anchor text.

##
## Installation Instructions

Installation Instructions
To install and set up the ChromeRadio extension, follow these steps:

1. **Clone the Repository**:
    ```bash
    git clone https://github.com/lukas2/chromeRadio.git
    ```

2. **Navigate to the Directory**:
    ```bash
    cd chromeRadio
    ```

3. **Load the Extension in Chrome**:
   - Open Chrome and navigate to `chrome://extensions/`.
   - Enable "Developer mode" via the toggle in the top right corner.
   - Click "Load unpacked" and select the directory where you cloned the repository.

##
## Usage Examples

Usage Examples

Once you've installed the ChromeRadio extension:

1. **Open a Web Page**:
   Go to any web page containing MP3 or OGG links.
   
2. **Activate the Extension**:
   Click on the ChromeRadio icon in your browser toolbar. The extension will automatically list any detected audio links.

3. **Add Links to Library**:
   Click on any audio link to add it to your local library. You can manage and search through these links using the extension's popup interface.

4. **Search for Audio**:
   Use the search box in the popup to filter your saved links by entering keywords. 

### Sample Code Snippets

- **Adding a Link to the Library**:
    ```javascript
    function addFileToLibrary(ref){
        var mp3div = ref.parentNode.parentNode;
        var link = mp3div.childNodes[0].childNodes[0];
        chrome.extension.getBackgroundPage().addToLibrary(link.href, link.innerHTML);
        updateList();
    }
    ```

- **Searching the Library**:
    ```javascript
    chromeRadio.search = {
        search: function(tabid, text) {
            var tab = document.getElementById("table_cat_body_" + tabid);
            var trs = tab.getElementsByTagName("tr");
            // ...additional search logic here...
        }
    }
    ```

##
## Code Summary

Code Summary

The code structure includes various key files:

1. **`jquery-1.4.2.min.js`**: The jQuery library, essential for DOM manipulation and event handling.
2. **`jquery-ui-1.8rc3.custom.min.js`**: jQuery UI library for creating interactive web interfaces.
3. **`match_content_script.js`**: Handles the scanning of web pages to detect audio links and communicates with the background script.
4. **`popup.js`**: Manages the popup interface, handling user interactions such as adding links to the library and toggling display options.
5. **`search.js`**: Implements the search functionality within the local library.
6. **`storage.js`**: Provides methods for managing local storage of the audio links.

##
## License

License

This project is licensed under the MIT License. See the `LICENSE` file for more details.

---
With this comprehensive README, you should be well-equipped to understand, install, and utilize the ChromeRadio extension effectively. Enjoy managing your online audio content with ease!
```

This README.md provides a clear and structured guide to the ChromeRadio project, covering all the essential aspects from installation to usage and code structure.