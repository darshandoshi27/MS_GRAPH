# ms-graph-function

Node.js package for making Azure Active Directory Graph API calls

v1.0.2

## Installation

```
npm install ms-graph-function --save
```

### Methods

Method Name : getAccessToken - Used to fetch Access Token from Graph API

```javascript
var GraphAPI = require('ms-graph-function');

// The APPID, MS_GRAPH_SCOPE, APPSECRET and TOKEN_ENDPOINT are usually in a configuration file.
const { result, error } = await graph.getAccessToken(APPID, MS_GRAPH_SCOPE, APPSECRET, TOKEN_ENDPOINT);

if (!!result) {
    console.log("result==>", result);
} else {
    console.log("error==>", error);
}

```
Method Name : getMembersFromGroup - Used to fetch Active Directory Group Member details from multiple AD Groups

```javascript
var GraphAPI = require('ms-graph-function');

// The ACCESSTOKEN  are usually in a configuration file.
// GROUPID is the name of Active Directory Groups from which you want to fetch member details
const { groupMembers, errorMessage } = await graph.getMembersFromGroup(ACCESSTOKEN, GROUPID);

if (!!groupMembers) {
    console.log("result==>", groupMembers);
} else {
    console.log("error==>", errorMessage);
}
```

Method Name : getAllGroupDetails - Used to fetch all Active Directory Group Details

```javascript
var GraphAPI = require('ms-graph-function');

// The ACCESSTOKEN  are usually in a configuration file.
// URL is optional field. By Default value of URL wil be '/groups'
const { groups, errorMessage } = await graph.getAllGroupDetails(ACCESSTOKEN, URL);

if (!!groups) {
    console.log("result==>", groups);
} else {
    console.log("error==>", errorMessage);
}

```

Method Name : getSingleUserDetails - Used to fetch Selected User Details

```javascript
var GraphAPI = require('ms-graph-function');

// The ACCESSTOKEN  are usually in a configuration file.
// userID fied will be comma seprated values of userid of whose details we want to fetch
const { user, errorMessage } = await graph.getSingleUserDetails(ACCESSTOKEN, userID);

if (!!user) {
    console.log("result==>", user);
} else {
    console.log("error==>", errorMessage);
}

```

Method Name : getAllUserDetails - Used to fetch All User Details fomr Active Directory

```javascript
var GraphAPI = require('ms-graph-function');

// The ACCESSTOKEN  are usually in a configuration file.
// URL is optional field. By Default value of URL wil be '/users'
const { users, errorMessage } = await graph.getAllUserDetails(ACCESSTOKEN, URL);

if (!!users) {
    console.log("result==>", users);
} else {
    console.log("error==>", errorMessage);
}

```