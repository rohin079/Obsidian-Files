
To store any file in any object store like `S3 Bucket` we can't send the image through the backend because that's a heavy task. 

That's why we make use of presigned URL's. Basically whenever user sends a request to upload an image, it sends a request to backend which then sends a request to S3 for a custom pre-signed-url that allows it to generate a url with permission of uploading a single image.

anyone with that url can directly upload a single object to s3, we return the url to frotnend and the user uploads the image directly to S3 without sending the image to backend or storing the image in backend

![[Pasted image 20240512093850.png]]

After creating a S3 Bucket make it private and expose the S3 bucket over a CDN like AWS CloudFront because it is cheaper and it is distributed, more efficient.