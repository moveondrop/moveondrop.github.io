# Onboard #

In this section, drop user will find how to get onboarded with MoveOnDrop platform.


The boarding started with the process of creating an account to MoveOnDrop Dashboard and adding a website (The consumer of the Drop Service).
<br/>
<br/>
These are the steps that can be followed to accomplish a successful MoveOnDrop integration. <br/><br/>
1) Create an account by visiting the URL `https://app.moveondrop.com/auth/register`. For Sandbox the URL will be `https://staging.moveon-drop-dashboard.pages.dev/auth/register`. <br/>
2) Once registration has been done, drop user needs to Log in to the dashboard. <br/>
3) Drop user will find a `Add a website` button in `Websites` sections of the dashboard. <br/>
4) Then drop user needs to create a new website by giving `website name` and `redirect url` as input. <br/>
  1) MoveOn will send an authorization code to this `redirect url` after approving the authorization request. The detail of the authorization flow can be found in the Authentication section of this API doc. <br/>


### Base URL's for MoveOnDrop Platform ###

| Name                         | Sandbox                                           | Production                        |
|------------------------------|---------------------------------------------------|-----------------------------------|
| `BASE_URL`                   | `https://api.sandbox.moveon.work`                 | `https://moveon.com.bd`           |
| `Authorization server login` | `https://api.sandbox.moveon.work/web/login`       | `https://moveon.com.bd/web/login` |
| `MoveOnDrop Dashboard`       | `https://staging.moveon-drop-dashboard.pages.dev` | `https://app.moveondrop.com`      |
