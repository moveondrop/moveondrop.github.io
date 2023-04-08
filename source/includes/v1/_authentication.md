# Authentication #

The Authentication API allows you to create and refresh access token.
Access token is required to access the MoveOn API.

Once a website has been added at MoveOnDrop Dashboard,
drop user may use the corresponding client ID and secret for that website
to request an authorization code from MoveOn.

First, the consuming application should make a redirect request
to MoveOn's `/web/oauth/authorize` route like so:

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-post">GET</i>
		<h6>/web/oauth/authorize</h6>
	</div>
</div>

### Request ###

### Available query parameters ###

| Attribute       | Type                        | Description                                                         |
|-----------------|-----------------------------|---------------------------------------------------------------------|
| `client_id`     | string                      | Client Id of the website                                            |
| `redirect_uri`  | string                      | Redirect URL of the website                                         |
| `response_type` | string(default value: code) | Response type you're expecting. Keep the value to 'code' by default |


```phpt
    $query = http_build_query([
        'client_id'     => 'client-id',
        'redirect_uri'  => 'https://consumer-website.com/callback',
        'response_type' => 'code',
        'scope'         => ''
    ]);
 
    return redirect('BASE_URL/web/oauth/authorize?'.$query);
```
#Approving The Request

When receiving authorization request, drop user could see a login screen of MoveOn authorization Server.
Drop user need to log in to the authorization server by using the same credential that has been used to access the MoveOnDrop Dashboard.
After login to the authorization server it's possible to approve or deny the authorization request. 
If the drop user approve the request, they will be redirected back to the redirect_uri that was specified in authorization request parameter.
The redirect_uri must match the redirect URL that was specified when the website was created at MoveOnDrop Dashboard.


##Converting Authorization Codes To Access Tokens

If the drop user approves the authorization request, they will be redirected back to the consuming application. 
An authorization code can be found in the query parameter of the redirected path.
Then the drop user should issue a POST request to MoveOn to request an access token. 
The request should include the authorization code that was issued by 
MoveOn when the drop user approved the authorization request:

```phpt
    $response = Http::asForm()->post('BASE_URL/web/oauth/token', [
        'grant_type'    => 'authorization_code',
        'client_id'     => 'Website client-id',
        'client_secret' => 'Website secret',
        'redirect_uri'  => 'https://consumer-website.com/callback',
        'code'          => $request->code, // authorization code found in redirected path
    ]);
 
    return $response->json();
```
This `/web/oauth/token` route will return a JSON response containing access_token, refresh_token, and expires_in attributes.
The expires_in attribute contains the number of seconds until the access token expires.

| Attribute             | Type    | Description                                         |
|-----------------------|---------|-----------------------------------------------------|
| `access_token`        | string  | Bearer token to access the MoveOn API               |
| `refresh_token`       | string  | Refresh token to refresh the access token in future |
| `expires_in`          | integer | The number seconds until the access token expires   |

# Refreshing Tokens
MoveOn issues short-lived access token, drop user will need to refresh their access token via refresh token 
that was provided to them when the access token was issued.

Example code to refresh the access token by using refresh token

```phpt
$response = Http::asForm()->post('`BASE_URL`/web/oauth/token', [
'grant_type'    => 'refresh_token',
'refresh_token' => 'the-refresh-token',
'client_id'     => 'website client-id',
'client_secret' => 'website secret',
'scope'         => '',
]);

return $response->json();
```


This `/web/oauth/token` route will return a JSON response containing following attributes.

access_token, refresh_token, and expires_in attributes. The expires_in attribute contains the number of seconds until the access token expires.


| Attribute             | Type    | Description                                         |
|-----------------------|---------|-----------------------------------------------------|
| `access_token`        | string  | Bearer token to access the MoveOn API               |
| `refresh_token`       | string  | Refresh token to refresh the access token in future |
| `expires_in`          | integer | The number seconds until the access token expires   |
