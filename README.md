# Scrappy Class

The `Scrappy` class provides functionality for web scraping using Selenium.

## Constructor

### `__init__(self, script=None, browser=None, show=False, debug=False, strict=False)`

The constructor initializes a `Scrappy` object with the following parameters:

- `script` (optional): The JavaScript code to be executed by the web browser.
- `browser` (optional): An existing instance of a Selenium WebDriver. If not provided, a new instance will be created using Chrome.
- `show` (optional): Boolean value indicating whether to show the browser window. Default is `False`.
- `debug` (optional): Boolean value indicating whether to enable debug mode. Default is `False`.
- `strict` (optional): Boolean value indicating whether to enable strict mode. Default is `False`.

## Methods

### `setup_browser(self)`

This method sets up the web browser instance. It creates a new instance of a Chrome WebDriver with the specified options based on the constructor parameters.

### `set_script(self, script)`

This method sets the JavaScript code to be executed by the web browser.

- `script`: The JavaScript code to be executed.

### `scrap(self, url, wait=False, wait_for=None, wait_target=None, wait_time=10)`

This method performs web scraping on the specified URL.

- `url`: The URL to scrape.
- `wait` (optional): Boolean value indicating whether to wait for an element to be present on the page before scraping. Default is `False`.
- `wait_for` (optional): The method to use for locating the element to wait for. Possible values are `'class'`, `'id'`, `'name'`, `'tag'`, `'link'`, `'part_link'`, `'css'`, or `'xp'`. Default is `None`.
- `wait_target` (optional): The target value to locate the element to wait for. Default is `None`.
- `wait_time` (optional): The maximum time (in seconds) to wait for the element to be present. Default is `10`.

Returns the result of executing the JavaScript code on the web page.

### `end(self)`

This method terminates the web browser instance if it exists.

## How to Use

1. Import the necessary modules:

    ```python
    from selenium import webdriver
    from selenium.webdriver.chrome.options import Options
    from selenium.webdriver.common.by import By
    from selenium.webdriver.support.ui import WebDriverWait
    from selenium.webdriver.support import expected_conditions as EC
    ```

2. Create an instance of the Scrappy class:

    ```python
    scrappy = Scrappy()
    ```

3. Use the scrap method to scrape a webpage:

    ```python
    result = scrappy.scrap(url, wait=True, wait_for='id', wait_target='elementId')
    ```

4. Retrieve the result of the scraping operation:

    ```python
    print(result)
    ```

5. Terminate the web browser instance when finished:

    ```python
    scrappy.end()
    ```

Please note that you will need to have the necessary `Selenium` and `WebDriver` dependencies installed to use this code.
