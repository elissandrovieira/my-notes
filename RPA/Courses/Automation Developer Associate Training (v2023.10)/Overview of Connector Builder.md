## 🗺️Overview 

Connector Builder is a powerful feature in UiPath Studio that empowers users to design and use custom connectors. By harnessing the capabilities of Connector Builder, users can effortlessly establish connections between different applications and services.

With Connector Builder, you can construct first-class connectors tailored to your specific needs.

---

## 🔌Connector Builder allows users to interact with the following features:

1. **Integration with the Integration Service:** The Connector Builder experience will be seamlessly integrated into the Integration Service, enabling users to create and utilize custom connectors directly from UiPath Studio.

2. **Custom Connectors in Studio Web Automation Cloud:** Users will have the capability to use their custom connectors in the Studio Web Automation Cloud, providing them with flexibility and access to their connectors from anywhere.

3. **Publishing and Sharing Custom Connectors:** Automation Cloud will include the Connector Builder feature, empowering users to publish and share their customized connectors with others. This fosters collaboration among users and enhances the overall automation experience by expanding the pool of available connectors.

---

## 🙆‍♂️Anatomy of a 'Connector Builder'

Application APIs come in various formats and structures, each offering unique characteristics and functionalities. Here are some of the key aspects that differentiate different APIs: 

- **API Technologies**
	APIs are built using various technologies, and some of the commonly used ones include REST, ODATA, SOAP, and others. Each technology has its own set of rules and protocols for communication and data exchange. 
	
- **API Documentation**
	To help developers understand and interact with APIs effectively, documentation is provided. API documentation can be in formats such as Swagger, Postman collections, WSDL (Web Services Description Language), or ODATA definitions. 
	
- **Authentication Types**
	APIs require authentication to ensure secure access. Different authentication types are used, including OAuth 2.0, basic authentication, API keys, and custom headers, each providing different levels of security and access control. 
	
- **Payload Formats**
	APIs can exchange data in various formats. JSON (JavaScript Object Notation) and XML (Extensible Markup Language) are common payload formats, though JSON is widely favored due to its simplicity and ease of use.
	
- **HTTP Methods**
	APIs support different HTTP methods for different actions. Common methods include POST (for creating data), GET (for retrieving data), PUT (for updating data), and PATCH (for partial updates), among others.
	
- **Parameters**
	APIs use parameters to pass information and customize requests. Parameters can be included in various parts of the API call, such as headers, query strings, or request bodies.
	
- **Pagination**
	For APIs that return large datasets, pagination techniques are employed to break the results into manageable chunks. Common pagination methods include using an offset or cursor.
	
- **Search Capabilities**
	Many APIs offer search functionality, allowing users to query specific data based on parameters or search terms. Users can often filter data based on specific fields or conditions.

---

## 🔌The 'Connector Builder' supports the following authentication methods: 

- **OAuth 2.0 Authorization Code**: this method involves obtaining an authorization code from the API provider after the user grants permission. The code is then exchanged for an access token, which is used to access protected resources on behalf of the user.

- **OAuth 2.0 Authorization Code with PKCE**: this enhanced version of the previous method adds a Proof Key for Code Exchange (PKCE) to improve security for mobile and native applications.

- **OAuth 2.0 Client Credentials**: in this method, the application itself (not a specific user) obtains an access token to access protected resources directly from the API provider.

- **Basic Authentication**: this is a simple authentication method where the user's credentials (username and password) are sent as a base64-encoded string in the HTTP header.

- **API Key**: an API Key is a unique alphanumeric code that acts as a credential to authenticate API requests. It's often used for simple authentication and to track API usage.

- **Personal Access Token (PAT)**: a Personal Access Token is a type of token used for authentication, particularly in scenarios where a user interacts with APIs on their own behalf.

- **No Authentication**: some APIs may allow anonymous access, meaning no authentication is required to access the resources.

---

## 🧩Let's see how it works

In this demo, we are using Studio version 2022.10.
[![](https://embed-ssl.wistia.com/deliveries/fa2f9d80bd260bd9cbcc68f35ea257c23409d5d9.jpg?image_play_button_size=2x&image_crop_resized=960x540&image_play_button_rounded=1&image_play_button_color=595959e0)](https://cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Ffast.wistia.net%2Fembed%2Fiframe%2Fn7bmfgbdxz%3Fseo%3Dtrue%26videoFoam%3Dtrue&display_name=Wistia%2C%2BInc.&url=https%3A%2F%2Fuipathvideos.wistia.com%2Fmedias%2Fn7bmfgbdxz%3FembedType%3Diframe%26amp%3Bseo%3Dtrue%26amp%3BvideoFoam%3Dtrue%26amp%3BvideoWidth%3D640&image=https%3A%2F%2Fembed-ssl.wistia.com%2Fdeliveries%2Ffa2f9d80bd260bd9cbcc68f35ea257c23409d5d9.jpg%3Fimage_crop_resized%3D640x360&key=40cb30655a7f4a46adaaf18efb05db21&type=text%2Fhtml&schema=wistia&wvideo=n7bmfgbdxz)
