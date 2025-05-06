# Fork a collection
* If you want to work with a collection and it is not yours
* Go to that collection and on right click, Fork
* And import it into your workspace
* It creates a copy in ur workspace so ucan work on it


# SHare a collection
* click on collection, on right click,click no share
* Share via API
* Generate new key
* And then you will see a link, copy it and share
* This link always updated to new changes of that collection
* And this link shows info of that collection in JSON form




https://api.postman.com/collections/42789920-d7b18cea-a543-4936-8967-bb0ff5ab7dc0?access_key=PMAT-01JTJPQ1YRTGTJZMXGD0E14ZQ7


```json
{
    "collection": {
        "info": {
            "_postman_id": "d7b18cea-a543-4936-8967-bb0ff5ab7dc0",
            "name": "Library api vw",
            "schema": "https://schema.getpostman.com/json/collection/v2.1.0/collection.json",
            "updatedAt": "2025-05-06T11:34:48.000Z",
            "createdAt": "2025-05-05T12:28:40.000Z",
            "lastUpdatedBy": "42789920",
            "uid": "42789920-d7b18cea-a543-4936-8967-bb0ff5ab7dc0"
        },
        "item": [
            {
                "name": "New Request",
                "id": "6330ba77-a42a-4cbe-b267-842cc88ae6b1",
                "protocolProfileBehavior": {
                    "disableBodyPruning": true
                },
                "request": {
                    "method": "GET",
                    "header": [],
                    "url": {
                        "raw": "{{baseURL}}/books?genre=fiction&checkedOut=true",
                        "host": [
                            "{{baseURL}}"
                        ],
                        "path": [
                            "books"
                        ],
                        "query": [
                            {
                                "key": "genre",
                                "value": "fiction"
                            },
                            {
                                "key": "checkedOut",
                                "value": "true"
                            }
                        ]
                    }
                },
                "response": [],
                "uid": "42789920-6330ba77-a42a-4cbe-b267-842cc88ae6b1"
            },
            {
                "name": "{{baseURL}}/books/:id/3",
                "id": "0319ac36-0446-4c36-b279-d2ec41623cc3",
                "protocolProfileBehavior": {
                    "disableBodyPruning": true
                },
                "request": {
                    "auth": {
                        "type": "noauth"
                    },
                    "method": "GET",
                    "header": [],
                    "url": {
                        "raw": "{{baseURL}}/books/29cd820f-82f9-4b45-a7f4-0924111b5b89",
                        "host": [
                            "{{baseURL}}"
                        ],
                        "path": [
                            "books",
                            "29cd820f-82f9-4b45-a7f4-0924111b5b89"
                        ]
                    }
                },
                "response": [],
                "uid": "42789920-0319ac36-0446-4c36-b279-d2ec41623cc3"
            },
            {
                "name": "add a book",
                "event": [
                    {
                        "listen": "test",
                        "script": {
                            "id": "c6150059-0bf2-4ee1-b8c3-cc19db4edc5c",
                            "exec": [
                                "console.log(pm.response.json())\r",
                                "const new_book_id = pm.response.json().id \r",
                                "pm.collectionVariables.set(\"new_book_id\", new_book_id)"
                            ],
                            "type": "text/javascript",
                            "packages": {}
                        }
                    }
                ],
                "id": "681ea979-32d2-4dcb-97e4-389db504f2a3",
                "protocolProfileBehavior": {
                    "disableBodyPruning": true
                },
                "request": {
                    "method": "POST",
                    "header": [],
                    "body": {
                        "mode": "raw",
                        "raw": "{\r\n  \"title\": \"BRL Book 3\",\r\n  \"author\": \"BRL\",\r\n  \"genre\": \"delulu\",\r\n  \"yearPublished\": 2004\r\n}",
                        "options": {
                            "raw": {
                                "language": "json"
                            }
                        }
                    },
                    "url": {
                        "raw": "{{baseURL}}/books",
                        "host": [
                            "{{baseURL}}"
                        ],
                        "path": [
                            "books"
                        ]
                    }
                },
                "response": [],
                "uid": "42789920-681ea979-32d2-4dcb-97e4-389db504f2a3"
            }
        ],
        "auth": {
            "type": "apikey",
            "apikey": [
                {
                    "key": "in",
                    "value": "header",
                    "type": "string"
                },
                {
                    "key": "value",
                    "value": "postmanrulz",
                    "type": "string"
                },
                {
                    "key": "key",
                    "value": "api-key",
                    "type": "string"
                }
            ]
        },
        "event": [
            {
                "listen": "prerequest",
                "script": {
                    "id": "7eb124c4-b77f-44c5-afc2-3838d4dc4918",
                    "type": "text/javascript",
                    "packages": {},
                    "exec": [
                        ""
                    ]
                }
            },
            {
                "listen": "test",
                "script": {
                    "id": "2f63f5e9-7603-4193-9b68-0651c2849e36",
                    "type": "text/javascript",
                    "packages": {},
                    "exec": [
                        ""
                    ]
                }
            }
        ],
        "variable": [
            {
                "key": "baseURL",
                "value": "https://library-api.postmanlabs.com",
                "type": "default"
            },
            {
                "key": "new_book_id",
                "value": ""
            }
        ]
    }
}
```
