# Document Render FAQs

Here you can find a variety if frequently asked questions regarding the Document Render platform.

 
## Where can I find example templates in GitHub?

Unfortunately, the Document Render platform does not leverage the templates that are stored in source code, and there is no mandatory requirement to store the template in Git if you wish to leverage this platform. Instead, templates are stored in S3 in the Assets Registry bucket.

It is best practice for individual consumer services to track their template(s) in source code for traceability and review purposes. See [Dissolution API](https://github.com/companieshouse/dissolution-api) for an example.

## Java WebClient complains about an invalid Content-Type when trying to provide JSON data for the template

A HTTP request’s `Content-Type` header should represent the type of the request body being sent. For forms this is usually `multipart/form-data` and for APIs this is usually `application/json`.

However, the [Swagger](https://github.com/companieshouse/document-render-service/blob/master/spec/swagger.json) outlines that the Content-Type of the Document Render POST request represents the type of the template, in which case is currently always `text/html`.

To workaround the Java error, convert the JSON object → JSON string, and transmit it as String data.

## Document Render from HTML5 fails to start in local Docker development environment.

This can happen when the Assets Registry service is still initialising while the HTML5 service starts. 9 times out of 10 this can be resolved by:

1. Restart the Assets Registry service
2. Wait for it to finish initialising
3. Restart the HTML5 service

## Navigation

- [back](../README.md)