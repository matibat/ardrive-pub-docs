# Content Types

All transaction types in ArFS leverage a specific metadata tag for the Content-Type (also known as mime-type) of the data that is included in the transaction. ArFS clients must determine what the mime-type of the data is, in order for Arweave gateways and browswers to render this content appropriately.

All public drive, folder, and file (metadata only) entity transactions all use a JSON standard, therefore they must have the following content type tag:

```
Content-Type: '<application/json>'
```

However, a file's data transaction must have its mime-type determined. This is stored in the file's corresponding metadata transaction JSON's `dataContentType` as well as the content type tag in the data transaction itself.

```
Content-Type: "<file's mime-type>"
```

All private drive, folder, and file entity transactions must have the following content type, since they are encrypted:

```
Content-Type: '<application/octet-stream>'
```

<mark style="background: #d3d3d3; font-size: 200%">ArDrive-Core includes methods to determine a file's content type</mark>


## Other Tags

ArFS enabled clients should include the following tags on their transactions to identify their application

```
App-Name: "<defined application name eg. ArDrive"
App-Version: "<defined version of the app eg. 0.5.0"
Client?: "<if the application has multiple clients, they should be specified here eg. Web" 
```



