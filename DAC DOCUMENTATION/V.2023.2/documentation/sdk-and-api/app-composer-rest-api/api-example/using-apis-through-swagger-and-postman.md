# Using APIs through Swagger and Postman

## Using the API through Swagger

In this example, you'll learn how to create a token to test APIs in Swagger's documentation.

{% embed url="https://app.arcade.software/share/bhx5IyV4Wh4qnsCgS1US" %}

## Using the API through Postman

Now let's see how the API from the previous example is executed in Postman.

<figure><img src="../../../../.gitbook/assets/image (28).png" alt=""><figcaption></figcaption></figure>

In this case the token must be passed in the header of the request:

* `Authorization: Bearer <DAC Token>`
* With the `Accept` header, you specify the type of response that the client receives from the server, which in this case is `JSON`.
