# Create Language Translator Service Instance

## Objective

IBM Watson™ Language Translator allows you to translate text programmatically from one language into another language.

You create an instance of IBM Watson™ Language Translator service in IBM Cloud.

## Tools Used

* Watson Language Translator

## Requirements

* [IBM Cloud Account](https://cloud.ibm.com)

## Steps

To create an instance of IBM Watson™ Language Translator service in IBM Cloud,

1. login to [IBM Cloud](https://cloud.ibm.com).
2. Select [Catalog](https://cloud.ibm.com/catalog) from the top navigation bar.
3. Search for `language translator`.
4. Select the `Language Translator` tile.
5. Select a region, for example `Dallas`.
6. Select an `Advanced` or `Premium` pricing plan.

   > Note: Because, you are going to build a custom model with your dictionary, you must select an `Advanced` or `Premium` pricing plan.

7. Give it a unique name, for example `my-Language-Translator`.
8. Select `Both public & prvate network` for the `Service Endpoints`.
9. Accept the default for the rest of settings.
10. Click `Create` button. This create your `Translator` insstance.

### Setup a terminal environment connecting to `Translator` instance

The rest of the workshop will use your `Translator` instance created in this section. For simplicity, you are going to connect to your `Translator` instance via `Curl` command in a terminal wiindow. To connect to your `Translator` instance, `API key` and `Endpoint URL` must be set correctly.

1. Go back to the browser where you have created your `Translator` instance.
2. Select `Manage` in the left navigation pane.
3. Both `API key` and `URL` are available on the right.

   ![Translator service](.gitbook/assets/translator-service.png)

4. Copy the `API key`.
5. Open a terminal window.
6. Execute command

   ```text
    export apikey=<your API key>
   ```

7. Copy the `URL`.
8. Execute command below in the terminal window.

   ```text
    export url=<your url>
   ```

9. To verify you are connected to an instance `Translator` service, execute the command

   ```text
    curl --user "apikey:$apikey" "$url/v3/models?source=en&target=es&version=2018-05-01"
   ```

10. It should return

    ```text
     {
         "models" : [ {
             "model_id" : "en-es",
             "source" : "en",
             "target" : "es",
             "base_model_id" : "",
             "domain" : "general",
             "customizable" : true,
             "default_model" : true,
             "owner" : "",
             "status" : "available",
             "name" : "en-es",
             "training_log" : null
         } ]
     }
    ```

11. If the expected result were not returned, reset both `apikey` and `url` environment variable.

## Related Links

There is lots of great information, tutorials, articles, etc on the [IBM Developer site](https://developer.ibm.com) as well as broader web. Here are a subset of good examples related to data understanding, visualization and processing:

* [Getting started with Language Translator](https://cloud.ibm.com/docs/language-translator?topic=language-translator-gettingstarted)
* [IBM Cloud API Docs - Language Translator](https://cloud.ibm.com/apidocs/language-translator)

## General Links

* [IBM Developer](https://developer.ibm.com)

