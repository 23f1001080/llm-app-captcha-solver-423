# Project Title

Multiple CAPTCHA Solver

## Description (what the app does)

This web application solves multiple CAPTCHA images using Google's Gemini Vision API. It accepts multiple CAPTCHA image URLs as query parameters (url1, url2, url3, etc.), displays the images side-by-side, and uses the Gemini API to extract the text from each image. The solved CAPTCHA text is then displayed below each image, along with individual loading indicators while processing.

## Setup Instructions (how to clone and run)

1.  Clone the repository:

    ```bash
    git clone <repository_url>
    cd <project_directory>
    ```

2.  Open `index.html` in your web browser.

## Usage Guide (how to use the features)

1.  Provide the CAPTCHA image URLs as query parameters in the URL.

    ```
    index.html?url1=<CAPTCHA_IMAGE_URL_1>&url2=<CAPTCHA_IMAGE_URL_2>&url3=<CAPTCHA_IMAGE_URL_3>
    ```

    Replace `<CAPTCHA_IMAGE_URL_1>`, `<CAPTCHA_IMAGE_URL_2>`, `<CAPTCHA_IMAGE_URL_3>` with the actual URLs of the CAPTCHA images.

2.  The application will display the CAPTCHA images and individual loading indicators.
3.  After processing, the solved CAPTCHA text will be displayed below each image.

## Code Explanation (explain the main code logic in index.html, CSS, JS)

### HTML Structure

The `index.html` file contains the basic HTML structure for the web page. It includes a container div that holds the heading and a `captcha-container` div.  The `captcha-container` dynamically creates divs for each CAPTCHA image, loading indicator, and result section.

### JavaScript Functions

-   **`getParameterByName(name, url)`**: This function extracts the value of a query parameter from the URL.
-   **`solveCaptcha(imageUrl, index)`**: This function calls the Gemini Vision API to solve the CAPTCHA. It sends the image URL to the API and returns the extracted text.  It requires an API key to be set. The index is used to target the correct loading indicator.
-   **`main()`**: This function is the main entry point of the script. It gets the image URLs from the query parameters, dynamically creates image elements, calls `solveCaptcha` for each image, and displays the solved text. It also handles the loading indicators and error cases.

### API Calls and Data Processing Logic

-   The `solveCaptcha` function makes a `POST` request to the Gemini Vision API endpoint.
-   The request body includes the image data and a text prompt asking the API to identify the characters in the image.
-   The API response is parsed to extract the solved CAPTCHA text.
-   A timeout of 15 seconds is implemented to prevent the application from waiting indefinitely for the API response.

## License (full MIT License text)

MIT License

Copyright (c) 2025 23f1001080

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
