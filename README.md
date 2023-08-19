Story Spoil API:

This section provides information about the Story Spoil API endpoints and their functionalities. It serves as a guide to understand how to interact with the Story Spoil API.
https://d5wfqm7y6yb3q.cloudfront.net/

Methods supported:
You can see all the supported methods on the following link: [Methods](https://d5wfqm7y6yb3q.cloudfront.net/)

The following endpoints are supported:
1. User
• POST /api/User/Create – create a new post a JSON object in the request body, e.g. { "userName": "string","firstName": "string", "midName": "string", "lastName": "string", "email": "user@example.com", "password": "string", "rePassword": "string" }
• POST /api/User/Authentication: log in an existing user (post a JSON object in the request body, e.g. { "userName": "string", "password": "string"})
Access Token
• When a user logs in, the response format is JSON object, e.g. {"userName": "string", "password": "1234567", "accessToken": "eyJhbGciOiJ…"}
NB! Access token is needed for all spoiler requests. It should be placed under the Authorization tab, Bearer Token option.

3. Spoiler
All of the following requests require Authotization. • GET /api/Story/All – list all spoilers (empty request body) • GET /api/Story/Search – search spoilers by their name, requires queryParameter: ?keyword= storyTitle
• POST /api/Story/Create – create a new spoiler: post a JSON object in the request body, e.g. { "title": "string", "description": "string", "url": "" }
• PUT /api/Story/Edit/storyId – replace the existing spoiler with the new one: post a JSON object in the request body, e.g. {"title": "string", description": "string", "url": ""};
• DELETE /api/Story/Delete/storyId – delete existing spoiler;

Story Spoil API Tasks: Postman Requests
Your task is to write API requests with Postman for certain RESTful API endpoints. You should organize your requests in a collection.

1. Log in to the API
Send a POST request with your username and password, that you previously created from the Story Spoil Web App. If properly executed, you will receive your access token as a part of the response body. Use it as a Bearer Token in the Authorization section for the next requests.
2. Create a new spoiler
Send a POST request with the attributes needed for creating a new spoiler
Keep in mind that the full attributes in the JSON body are as follows:
{ "title": "string", "description": "string", "url": "http://...jpg" }
URL attribute is not mandatory, meaning that you can create a spoiler only with title and description. If you decide to use the url attribute, notice, that it has to point to a picture format or it can be left blank.
3. List all spoilers
Send a GET request to receive a list of all created spoilers.
This request will return all spoilers created through your profile. So, if you created any spoilers via the Web App, they also will be listed. In the list of spoilers, find the idea that you just created. You will need its id for the next request.
4. Change the title of the spoiler you created
Send a PUT request with the attributes needed to replace the spoiler you created in task number 2. "Create a new spoiler".
5. Delete Spoiler
Send a DELETE request with the attributes needed for deleting the spoiler you just edited.
