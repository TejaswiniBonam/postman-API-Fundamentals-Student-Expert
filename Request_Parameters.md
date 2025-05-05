# Request Parameters
* Postman allows you to save values as variables to reuse them and easily hide sensitive information like API Keys
* We will use a variable to replace our base URL so that we don't have to type that repeatedly. Once a variable is defined, you can access its value using double curly brace syntax like this: **{{variableName}}**

### Let's set a variable
* Let's make a variable for the host that we used in the previous request.
* select the url and right click, you'll see "Set as a variable"
* CLick that and give it a name
* **Variable Names are cAsE Sensitive**
* And then Define it's scope like Global, Collection, Vault..
* And DONE
* From then it'll be represented as {{name_of_variable}}

## Where to see the Variables???
* Click on your collection name and you can get to see the variable tab
* Seems like you can even modify the variable as there are two columns called "Initial Value" and "Current Value".

![instructor_26fp2261340y1ukokimvca8su_public_1649630820_baseUrl+1 1649630820044](https://github.com/user-attachments/assets/d2abce83-e22a-4e1e-8676-4c07421d0f39)


## Query Parameters
* Minimum things required to make an API call
    * Request Type (GET, POST, PUT, PATCH, DELETE...)
    * URL
* Sometimes api calls ALLOW some parameters that Key, Value pairs
* Key-Value pairs are represented within the URL.. They start with '?' and seperated with '='
* "URL?<key>=<value>
* There might be a case where there are more than one key-value pair
* And they are seperated by '&'
* URL?<key1>=<value1>&<key2>=<value2>
### Example
* If we search "Hello" in google it goes like
* https://google.com/search?q=Hello..........
* Here '/search' is the **PATH**
* Where <q, Hello> --> Key -value pairs where q stands for query

## When to use parameters?
* Based on the documentation of API


# TASK - Search books by genre
* In the previous API request, We wrote the call to retrieve ALL books
* Now, Let us try to filter by genre
* The API allows us to add query parameters to a GET /books request to filter the results, as shown under "Params." Check out the Postman Library API v2 documentation for detailed documentation.
* So acc to Postman library API , There are some params listed like, genre, checkout, Search
* SO we can filter out by genre
* And the URL goes like
      * https://library-api.postmanlabs.com/books?genre=fiction
      * https://library-api.postmanlabs.com/books?genre=fiction&checkedOut=true etc
* These will give the books that falls under those conditions


# Path Variable
* Another way of passing request data to an API is via path variables (a.k.a. "path parameters"). A path variable is a dynamic section of a path and is often used for IDs and entity names such as usernames.
* The path variable comes immediately after a slash in the path. For example, the GitHub API allows you to search for GitHub users by providing a username in the path in place of {username} below:
      * GET https://api.github.com/users/{username}
* Making this API call with a value for {username} will fetch data about that user:
      * https://api.github.com/users/TejaswiniBonam
```json
{
  "login": "TejaswiniBonam",
  "id": 130749202,
  "node_id": "U_kgDOB8sTEg",
  "avatar_url": "https://avatars.githubusercontent.com/u/130749202?v=4",
  "gravatar_id": "",
  "url": "https://api.github.com/users/TejaswiniBonam",
  "html_url": "https://github.com/TejaswiniBonam",
  "followers_url": "https://api.github.com/users/TejaswiniBonam/followers",
  "following_url": "https://api.github.com/users/TejaswiniBonam/following{/other_user}",
  "gists_url": "https://api.github.com/users/TejaswiniBonam/gists{/gist_id}",
  "starred_url": "https://api.github.com/users/TejaswiniBonam/starred{/owner}{/repo}",
  "subscriptions_url": "https://api.github.com/users/TejaswiniBonam/subscriptions",
  "organizations_url": "https://api.github.com/users/TejaswiniBonam/orgs",
  "repos_url": "https://api.github.com/users/TejaswiniBonam/repos",
  "events_url": "https://api.github.com/users/TejaswiniBonam/events{/privacy}",
  "received_events_url": "https://api.github.com/users/TejaswiniBonam/received_events",
  "type": "User",
  "user_view_type": "public",
  "site_admin": false,
  "name": "Renuka Lakshmi Tejaswini Bonam",
  "company": "@IBM",
  "blog": "https://www.linkedin.com/in/renuka-lakshmi-tejaswini-bonam-b87443255/",
  "location": "Bangalore",
  "email": null,
  "hireable": null,
  "bio": "Software Intern At IBM, 4rth year CSE Student. Graduate - 2025.\r\n",
  "twitter_username": null,
  "public_repos": 23,
  "public_gists": 0,
  "followers": 4,
  "following": 10,
  "created_at": "2023-04-14T09:21:53Z",
  "updated_at": "2025-04-23T17:49:52Z"
}
```
* You can have multiple path variables in a single request, such as this endpoint for getting a user's GitHub code repository:
      * GET https://api.github.com/repos/{owner}/{repoName}
      * https://api.github.com/repos/TejaswiniBonam/JavaScript
```json
{
  "id": 977498432,
  "node_id": "R_kgDOOkNxQA",
  "name": "JavaScript",
  "full_name": "TejaswiniBonam/JavaScript",
  "private": false,
  "owner": {
    "login": "TejaswiniBonam",
    "id": 130749202,
    "node_id": "U_kgDOB8sTEg",
    "avatar_url": "https://avatars.githubusercontent.com/u/130749202?v=4",
    "gravatar_id": "",
    "url": "https://api.github.com/users/TejaswiniBonam",
    "html_url": "https://github.com/TejaswiniBonam",
    "followers_url": "https://api.github.com/users/TejaswiniBonam/followers",
    "following_url": "https://api.github.com/users/TejaswiniBonam/following{/other_user}",
    "gists_url": "https://api.github.com/users/TejaswiniBonam/gists{/gist_id}",
    "starred_url": "https://api.github.com/users/TejaswiniBonam/starred{/owner}{/repo}",
    "subscriptions_url": "https://api.github.com/users/TejaswiniBonam/subscriptions",
    "organizations_url": "https://api.github.com/users/TejaswiniBonam/orgs",
    "repos_url": "https://api.github.com/users/TejaswiniBonam/repos",
    "events_url": "https://api.github.com/users/TejaswiniBonam/events{/privacy}",
    "received_events_url": "https://api.github.com/users/TejaswiniBonam/received_events",
    "type": "User",
    "user_view_type": "public",
    "site_admin": false
  },
  "html_url": "https://github.com/TejaswiniBonam/JavaScript",
  "description": null,
  "fork": false,
  "url": "https://api.github.com/repos/TejaswiniBonam/JavaScript",
  "forks_url": "https://api.github.com/repos/TejaswiniBonam/JavaScript/forks",
  "keys_url": "https://api.github.com/repos/TejaswiniBonam/JavaScript/keys{/key_id}",
  "collaborators_url": "https://api.github.com/repos/TejaswiniBonam/JavaScript/collaborators{/collaborator}",
  "teams_url": "https://api.github.com/repos/TejaswiniBonam/JavaScript/teams",
  "hooks_url": "https://api.github.com/repos/TejaswiniBonam/JavaScript/hooks",
  "issue_events_url": "https://api.github.com/repos/TejaswiniBonam/JavaScript/issues/events{/number}",
  "events_url": "https://api.github.com/repos/TejaswiniBonam/JavaScript/events",
  "assignees_url": "https://api.github.com/repos/TejaswiniBonam/JavaScript/assignees{/user}",
  "branches_url": "https://api.github.com/repos/TejaswiniBonam/JavaScript/branches{/branch}",
  "tags_url": "https://api.github.com/repos/TejaswiniBonam/JavaScript/tags",
  "blobs_url": "https://api.github.com/repos/TejaswiniBonam/JavaScript/git/blobs{/sha}",
  "git_tags_url": "https://api.github.com/repos/TejaswiniBonam/JavaScript/git/tags{/sha}",
  "git_refs_url": "https://api.github.com/repos/TejaswiniBonam/JavaScript/git/refs{/sha}",
  "trees_url": "https://api.github.com/repos/TejaswiniBonam/JavaScript/git/trees{/sha}",
  "statuses_url": "https://api.github.com/repos/TejaswiniBonam/JavaScript/statuses/{sha}",
  "languages_url": "https://api.github.com/repos/TejaswiniBonam/JavaScript/languages",
  "stargazers_url": "https://api.github.com/repos/TejaswiniBonam/JavaScript/stargazers",
  "contributors_url": "https://api.github.com/repos/TejaswiniBonam/JavaScript/contributors",
  "subscribers_url": "https://api.github.com/repos/TejaswiniBonam/JavaScript/subscribers",
  "subscription_url": "https://api.github.com/repos/TejaswiniBonam/JavaScript/subscription",
  "commits_url": "https://api.github.com/repos/TejaswiniBonam/JavaScript/commits{/sha}",
  "git_commits_url": "https://api.github.com/repos/TejaswiniBonam/JavaScript/git/commits{/sha}",
  "comments_url": "https://api.github.com/repos/TejaswiniBonam/JavaScript/comments{/number}",
  "issue_comment_url": "https://api.github.com/repos/TejaswiniBonam/JavaScript/issues/comments{/number}",
  "contents_url": "https://api.github.com/repos/TejaswiniBonam/JavaScript/contents/{+path}",
  "compare_url": "https://api.github.com/repos/TejaswiniBonam/JavaScript/compare/{base}...{head}",
  "merges_url": "https://api.github.com/repos/TejaswiniBonam/JavaScript/merges",
  "archive_url": "https://api.github.com/repos/TejaswiniBonam/JavaScript/{archive_format}{/ref}",
  "downloads_url": "https://api.github.com/repos/TejaswiniBonam/JavaScript/downloads",
  "issues_url": "https://api.github.com/repos/TejaswiniBonam/JavaScript/issues{/number}",
  "pulls_url": "https://api.github.com/repos/TejaswiniBonam/JavaScript/pulls{/number}",
  "milestones_url": "https://api.github.com/repos/TejaswiniBonam/JavaScript/milestones{/number}",
  "notifications_url": "https://api.github.com/repos/TejaswiniBonam/JavaScript/notifications{?since,all,participating}",
  "labels_url": "https://api.github.com/repos/TejaswiniBonam/JavaScript/labels{/name}",
  "releases_url": "https://api.github.com/repos/TejaswiniBonam/JavaScript/releases{/id}",
  "deployments_url": "https://api.github.com/repos/TejaswiniBonam/JavaScript/deployments",
  "created_at": "2025-05-04T10:54:22Z",
  "updated_at": "2025-05-04T12:34:27Z",
  "pushed_at": "2025-05-04T12:34:23Z",
  "git_url": "git://github.com/TejaswiniBonam/JavaScript.git",
  "ssh_url": "git@github.com:TejaswiniBonam/JavaScript.git",
  "clone_url": "https://github.com/TejaswiniBonam/JavaScript.git",
  "svn_url": "https://github.com/TejaswiniBonam/JavaScript",
  "homepage": null,
  "size": 10,
  "stargazers_count": 0,
  "watchers_count": 0,
  "language": null,
  "has_issues": true,
  "has_projects": true,
  "has_downloads": true,
  "has_wiki": true,
  "has_pages": false,
  "has_discussions": false,
  "forks_count": 0,
  "mirror_url": null,
  "archived": false,
  "disabled": false,
  "open_issues_count": 0,
  "license": null,
  "allow_forking": true,
  "is_template": false,
  "web_commit_signoff_required": false,
  "topics": [

  ],
  "visibility": "public",
  "forks": 0,
  "open_issues": 0,
  "watchers": 0,
  "default_branch": "main",
  "temp_clone_token": null,
  "network_count": 0,
  "subscribers_count": 1
}
```
