# BudgetsApi

All URIs are relative to *https://api.ynab.com/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**getBudgetById**](BudgetsApi.md#getBudgetById) | **GET** /budgets/{budget_id} | Single budget |
| [**getBudgetSettingsById**](BudgetsApi.md#getBudgetSettingsById) | **GET** /budgets/{budget_id}/settings | Budget Settings |
| [**getBudgets**](BudgetsApi.md#getBudgets) | **GET** /budgets | List budgets |


<a id="getBudgetById"></a>
# **getBudgetById**
> BudgetDetailResponse getBudgetById(budgetId, lastKnowledgeOfServer)

Single budget

Returns a single budget with all related entities.  This resource is effectively a full budget export.

### Example
```java
// Import classes:
import org.openapitools.client.ApiClient;
import org.openapitools.client.ApiException;
import org.openapitools.client.Configuration;
import org.openapitools.client.auth.*;
import org.openapitools.client.models.*;
import org.openapitools.client.api.BudgetsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.ynab.com/v1");
    
    // Configure HTTP bearer authorization: bearer
    HttpBearerAuth bearer = (HttpBearerAuth) defaultClient.getAuthentication("bearer");
    bearer.setBearerToken("BEARER TOKEN");

    BudgetsApi apiInstance = new BudgetsApi(defaultClient);
    String budgetId = "budgetId_example"; // String | The id of the budget. \"last-used\" can be used to specify the last used budget and \"default\" can be used if default budget selection is enabled (see: https://api.ynab.com/#oauth-default-budget).
    Long lastKnowledgeOfServer = 56L; // Long | The starting server knowledge.  If provided, only entities that have changed since `last_knowledge_of_server` will be included.
    try {
      BudgetDetailResponse result = apiInstance.getBudgetById(budgetId, lastKnowledgeOfServer);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling BudgetsApi#getBudgetById");
      System.err.println("Status code: " + e.getCode());
      System.err.println("Reason: " + e.getResponseBody());
      System.err.println("Response headers: " + e.getResponseHeaders());
      e.printStackTrace();
    }
  }
}
```

### Parameters

| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **budgetId** | **String**| The id of the budget. \&quot;last-used\&quot; can be used to specify the last used budget and \&quot;default\&quot; can be used if default budget selection is enabled (see: https://api.ynab.com/#oauth-default-budget). | |
| **lastKnowledgeOfServer** | **Long**| The starting server knowledge.  If provided, only entities that have changed since &#x60;last_knowledge_of_server&#x60; will be included. | [optional] |

### Return type

[**BudgetDetailResponse**](BudgetDetailResponse.md)

### Authorization

[bearer](../README.md#bearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested budget |  -  |
| **404** | The specified budget was not found |  -  |
| **0** | An error occurred |  -  |

<a id="getBudgetSettingsById"></a>
# **getBudgetSettingsById**
> BudgetSettingsResponse getBudgetSettingsById(budgetId)

Budget Settings

Returns settings for a budget

### Example
```java
// Import classes:
import org.openapitools.client.ApiClient;
import org.openapitools.client.ApiException;
import org.openapitools.client.Configuration;
import org.openapitools.client.auth.*;
import org.openapitools.client.models.*;
import org.openapitools.client.api.BudgetsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.ynab.com/v1");
    
    // Configure HTTP bearer authorization: bearer
    HttpBearerAuth bearer = (HttpBearerAuth) defaultClient.getAuthentication("bearer");
    bearer.setBearerToken("BEARER TOKEN");

    BudgetsApi apiInstance = new BudgetsApi(defaultClient);
    String budgetId = "budgetId_example"; // String | The id of the budget. \"last-used\" can be used to specify the last used budget and \"default\" can be used if default budget selection is enabled (see: https://api.ynab.com/#oauth-default-budget).
    try {
      BudgetSettingsResponse result = apiInstance.getBudgetSettingsById(budgetId);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling BudgetsApi#getBudgetSettingsById");
      System.err.println("Status code: " + e.getCode());
      System.err.println("Reason: " + e.getResponseBody());
      System.err.println("Response headers: " + e.getResponseHeaders());
      e.printStackTrace();
    }
  }
}
```

### Parameters

| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **budgetId** | **String**| The id of the budget. \&quot;last-used\&quot; can be used to specify the last used budget and \&quot;default\&quot; can be used if default budget selection is enabled (see: https://api.ynab.com/#oauth-default-budget). | |

### Return type

[**BudgetSettingsResponse**](BudgetSettingsResponse.md)

### Authorization

[bearer](../README.md#bearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The requested budget settings |  -  |
| **404** | The specified Budget was not found |  -  |
| **0** | An error occurred |  -  |

<a id="getBudgets"></a>
# **getBudgets**
> BudgetSummaryResponse getBudgets(includeAccounts)

List budgets

Returns budgets list with summary information

### Example
```java
// Import classes:
import org.openapitools.client.ApiClient;
import org.openapitools.client.ApiException;
import org.openapitools.client.Configuration;
import org.openapitools.client.auth.*;
import org.openapitools.client.models.*;
import org.openapitools.client.api.BudgetsApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://api.ynab.com/v1");
    
    // Configure HTTP bearer authorization: bearer
    HttpBearerAuth bearer = (HttpBearerAuth) defaultClient.getAuthentication("bearer");
    bearer.setBearerToken("BEARER TOKEN");

    BudgetsApi apiInstance = new BudgetsApi(defaultClient);
    Boolean includeAccounts = true; // Boolean | Whether to include the list of budget accounts
    try {
      BudgetSummaryResponse result = apiInstance.getBudgets(includeAccounts);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling BudgetsApi#getBudgets");
      System.err.println("Status code: " + e.getCode());
      System.err.println("Reason: " + e.getResponseBody());
      System.err.println("Response headers: " + e.getResponseHeaders());
      e.printStackTrace();
    }
  }
}
```

### Parameters

| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **includeAccounts** | **Boolean**| Whether to include the list of budget accounts | [optional] |

### Return type

[**BudgetSummaryResponse**](BudgetSummaryResponse.md)

### Authorization

[bearer](../README.md#bearer)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The list of budgets |  -  |
| **404** | No budgets were found |  -  |
| **0** | An error occurred |  -  |

