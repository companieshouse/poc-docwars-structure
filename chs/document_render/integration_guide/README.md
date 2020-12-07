# Document Render Integration Guide

This page outlines the steps that you will need to perform in order to successfully integrate with the Document Render platform.

The [Swagger documentation](https://github.com/companieshouse/document-render-service/blob/master/spec/swagger.json) provides detailed descriptions of each endpoint and their usage.

## 1. Create a template
A HTML template for your document must be uploaded to the Assets Registry S3 bucket (see `ASSET_BUCKET_NAME` environment variable for Assets Registry service). The template must be uploaded at the following path:

```
https://{ASSET_BUCKET_NAME}/{assetId}/templates/{templateName}
where the assetId and templateName are provided by the consumer service, for example:
```

```
https://{ASSET_BUCKET_NAME}/dissolution/templates/ds01.html
```

## 2. Upload fonts

*This part can be skipped if a HTML document is being generated.*

If you are generating a PDF, fonts must also be uploaded to the S3 bucket at the following location:

```
https://{ASSET_BUCKET_NAME}/{assetId}/fonts/{fontName}
```
which can be referenced in the HTML template using CSS:

```
font-family: '{fontName}'
```

## 3A. Generate and Return Document (NEED TO UPDATE)

*A sequence diagram can be found at Document Render Design  to visualise this guide.*

1. A call should be made to the Document Render Service’s `POST /document-render` endpoint, with the headers outlined in the Swagger.
2. The `assetId` and `templateName` headers are used to identify the HTML template in S3.
3. The `Content-Type` header represents the template type, usually `text/html`
4. The `Accept` header represents the type of the generated document, either `text/html` or `application/pdf`
5. The request body is used to parse the template and replace the placeholder values.
6. The generated document is returned in the response

## 3B. Generate and Store Document in S3
### __Prerequisite__
In order to store a generated document in S3, an S3 bucket must be available to output to. You can either reuse an existing bucket or create a dedicated bucket for your use case. Reusing buckets is recommended to reduce hitting AWS resource limits.

### __Guide__

The process is largely similar to that of the __Generate and return__ section above. The key differences are:

1. Use `POST /document-render/store` instead

2. Provide an additional `Location` header to represent where the generated document should be stored in S3

3. A `Location` header is returned that contains the S3 URL rather than the generated document itself.

The `Location` header can be provided in one of two ways:

### Auto generate file name

*Note that this value will be the default file name that a user will be pre-populated with upon trying to download the generated document, which may impact a user’s experience.*

A unique S3 file name will be automatically generated as a UUID. To do this, simply provide the S3 __directory__ where to output the generated document. For example, by providing a Location header of:

```
s3://{OUTPUT_BUCKET}/cidev/dissolution
```

then the generated S3 URL that is returned in the `Location` for a PDF would like something like:

```
s3://{OUTPUT_BUCKET}/cidev/dissolution/ds0139367dc3-bd2b-4155-a44c-7bf5768798b4.pdf
```

### Custom file name

To provide a custom file name, simply provide the full S3 path, including the file name. For example:

```
s3://{OUTPUT_BUCKET}/cidev/dissolution/ds0139367dc3-bd2b-4155-a44c-7bf5768798b4.pdf
```

and this will match the S3 URL returned in the `Location` header.

## Navigation

- [back](../README.md)