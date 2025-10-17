# Project Title

CAPTCHA Solver

## Description

This web application solves CAPTCHA images using Google's Gemini Vision API. It takes a CAPTCHA image URL as a query parameter, displays the image, and uses the Gemini API to extract the text from the image. The solved CAPTCHA text is then displayed on the page within 15 seconds, along with a loading indicator while processing.

## Setup Instructions

1.  Clone the repository:

    ```bash
    git clone <repository_url>
    cd <project_directory>
    ```

2.  Open `index.html` in your web browser.

## Usage Guide

1.  Provide the CAPTCHA image URL as a query parameter in the URL.

    ```
    index.html?url=<CAPTCHA_IMAGE_URL>
    ```

    Replace `<CAPTCHA_IMAGE_URL>` with the actual URL of the CAPTCHA image.

2.  The application will display the CAPTCHA image and a loading indicator.
3.  After processing, the solved CAPTCHA text will be displayed on the page.

## Code Explanation

### HTML Structure

The `index.html` file contains the basic HTML structure for the web page. It includes a container div that holds the heading, image, loading indicator, and result section. The CAPTCHA image is displayed using an `<img>` tag, and the solved text is displayed in a `<p>` tag. The loading indicator is a `<div>` that is shown while the API is processing the image.

### JavaScript Functions

-   **`getParameterByName(name, url)`**: This function extracts the value of a query parameter from the URL.
-   **`solveCaptcha(imageUrl)`**: This function calls the Gemini Vision API to solve the CAPTCHA. It sends the image URL to the API and returns the extracted text.  It requires an API key to be set.
-   **`main()`**: This function is the main entry point of the script. It gets the image URL from the query parameter, sets the image source, calls `solveCaptcha`, and displays the solved text. It also handles the loading indicator and error cases.

### API Calls and Data Processing Logic

-   The `solveCaptcha` function makes a `POST` request to the Gemini Vision API endpoint.
-   The request body includes the image data and a text prompt asking the API to identify the characters in the image.
-   The API response is parsed to extract the solved CAPTCHA text.
-   A timeout of 15 seconds is implemented to prevent the application from waiting indefinitely for the API response.

## License

MIT License

Copyright (c) [year] [fullname]

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.