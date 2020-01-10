# Convert any URL to PDF and/or HTML to PDF in PHP
PHP library to convert URLs and/or HTML to PDF via the PDFmyURL API service.

You can use the PDFmyURL API with a license from https://pdfmyurl.com. You can get a trial license at https://pdfmyurl.com/request-trial first if you like.

## Installation

You can install the library via Packagist as follows.

    $ composer require pdfmyurl/pdfmyurl
    
You can also just include the PDFmyURL.php file in your project from the src directory of course.

## Usage

Here's how you convert a URL to PDF in PHP with our API. You can download this example from the src directory.

    <?php
    require 'pdfmyurl.php';
    
    try {
    
      // first fill in the license that you received upon sign-up
      $pdf = new PDFmyURL ('your license here');
      
      // now set the options, so for example when we want to have a page in A4 in orientation portrait
      // you can also set these in our members area with a Wysiwig form by the way
      
      $pdf->SetPageSize('A4');
      $pdf->SetPageOrientation('Portrait');
      
      // then do the conversion - this is how you convert Google to PDF and display the PDF to the user
      $pdf->CreateFromURL ('www.google.com');
      $pdf->Display();
      
      // if you'd like to convert raw HTML instead you would have done this
      // $pdf->CreateFromHTML('<html><body>Hello World!</body></html>');
      // $pdf->Display();
      
      }  catch (Exception $error) {
       echo $error->getMessage();
       echo $error->getCode();
      }
      
More usage examples and documentation of this can be found at https://pdfmyurl.com/html-to-pdf-api-php-library

# License
The client library is licensed under the MIT license

# Contribution
Contribution is much appreciated! Reach out to support@pdfmyurl.com if you'd like to help!
