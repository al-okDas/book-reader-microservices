# Svadhyāy

## The backend repository for my book reader webapp

This is a repository for the backend of my book reader webapp. Checkout the [Front-End Repository][ui_github_repo] too.

The project is using Spring Cloud and microservice architecture. Following is the list of microservices used for the project:

* api-gateway-service
* service-discovery-service
* configuration-service
* book-service
* user-service
* uploader-service
* reader-service

The first 3 services are there for microservice architecture. The next 4 are services that expose APIs for the business logic.

## Book Service

This service has two main purposes. Firstly, it needs to persist the metadata of any new book that's added to the library. Then it offers APIs to get the details of books based on filters & search keywords.

1.  `/books/savebookdetails`
2.  `/books/getbookdetails/{ID}`

## Uploader Service

This has only one API, that takes a PDF file and saves the file in cloud storage. Simultaneously, it extracts the metadata and sends it to the user for confirmation, to be saved via book-service later.

1.  `/upload`

## User Service

This service will deal with providing data for authentication. Also, to store session details, any preferences, bookmarks & notes, this will expose some APIs. The list of services will evolve over time.

## Reader Service

This serves the purpose of sending the books in a chunked way in a scalable way, so that the front end can render them for the user.

1.  `/readbook/{booklD}/{pageNo}`



[ui_github_repo]: https://github.com/al-okDas/book-reader-ui.git "My Project Repository"