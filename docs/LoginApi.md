# dm_api_account.LoginApi

All URIs are relative to *http://localhost*

Method | HTTP request | Description
------------- | ------------- | -------------
[**v1_account_login_all_delete**](LoginApi.md#v1_account_login_all_delete) | **DELETE** /v1/account/login/all | Logout from every device
[**v1_account_login_delete**](LoginApi.md#v1_account_login_delete) | **DELETE** /v1/account/login | Logout as current user
[**v1_account_login_post**](LoginApi.md#v1_account_login_post) | **POST** /v1/account/login | Authenticate via credentials


# **v1_account_login_all_delete**
> v1_account_login_all_delete(x_dm_auth_token)

Logout from every device

### Example

```python
import time
import dm_api_account
from dm_api_account.api import login_api
from dm_api_account.model.general_error import GeneralError
from pprint import pprint
# Defining the host is optional and defaults to http://localhost
# See configuration.py for a list of all supported configuration parameters.
configuration = dm_api_account.Configuration(
    host = "http://localhost"
)


# Enter a context with an instance of the API client
with dm_api_account.ApiClient() as api_client:
    # Create an instance of the API class
    api_instance = login_api.LoginApi(api_client)
    x_dm_auth_token = "X-Dm-Auth-Token_example" # str | Authenticated requests require X-Dm-Auth-Token header. You can get the data from POST /account/ method, sending login and password in \"token\" response field
    x_dm_bb_render_mode = "X-Dm-Bb-Render-Mode_example" # str | Requests with user defined texts that allows usage of BB-codes may be rendered differently by passing the X-Dm-Bb-Render-Mode header of one of following values Html, Bb, Text, SafeHtml (optional)

    # example passing only required values which don't have defaults set
    try:
        # Logout from every device
        api_instance.v1_account_login_all_delete(x_dm_auth_token)
    except dm_api_account.ApiException as e:
        print("Exception when calling LoginApi->v1_account_login_all_delete: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Logout from every device
        api_instance.v1_account_login_all_delete(x_dm_auth_token, x_dm_bb_render_mode=x_dm_bb_render_mode)
    except dm_api_account.ApiException as e:
        print("Exception when calling LoginApi->v1_account_login_all_delete: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_dm_auth_token** | **str**| Authenticated requests require X-Dm-Auth-Token header. You can get the data from POST /account/ method, sending login and password in \&quot;token\&quot; response field |
 **x_dm_bb_render_mode** | **str**| Requests with user defined texts that allows usage of BB-codes may be rendered differently by passing the X-Dm-Bb-Render-Mode header of one of following values Html, Bb, Text, SafeHtml | [optional]

### Return type

void (empty response body)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: text/plain, application/json, text/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
**204** |  |  -  |
**401** | User must be authenticated |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **v1_account_login_delete**
> v1_account_login_delete(x_dm_auth_token)

Logout as current user

### Example

```python
import time
import dm_api_account
from dm_api_account.api import login_api
from dm_api_account.model.general_error import GeneralError
from pprint import pprint
# Defining the host is optional and defaults to http://localhost
# See configuration.py for a list of all supported configuration parameters.
configuration = dm_api_account.Configuration(
    host = "http://localhost"
)


# Enter a context with an instance of the API client
with dm_api_account.ApiClient() as api_client:
    # Create an instance of the API class
    api_instance = login_api.LoginApi(api_client)
    x_dm_auth_token = "X-Dm-Auth-Token_example" # str | Authenticated requests require X-Dm-Auth-Token header. You can get the data from POST /account/ method, sending login and password in \"token\" response field
    x_dm_bb_render_mode = "X-Dm-Bb-Render-Mode_example" # str | Requests with user defined texts that allows usage of BB-codes may be rendered differently by passing the X-Dm-Bb-Render-Mode header of one of following values Html, Bb, Text, SafeHtml (optional)

    # example passing only required values which don't have defaults set
    try:
        # Logout as current user
        api_instance.v1_account_login_delete(x_dm_auth_token)
    except dm_api_account.ApiException as e:
        print("Exception when calling LoginApi->v1_account_login_delete: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Logout as current user
        api_instance.v1_account_login_delete(x_dm_auth_token, x_dm_bb_render_mode=x_dm_bb_render_mode)
    except dm_api_account.ApiException as e:
        print("Exception when calling LoginApi->v1_account_login_delete: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_dm_auth_token** | **str**| Authenticated requests require X-Dm-Auth-Token header. You can get the data from POST /account/ method, sending login and password in \&quot;token\&quot; response field |
 **x_dm_bb_render_mode** | **str**| Requests with user defined texts that allows usage of BB-codes may be rendered differently by passing the X-Dm-Bb-Render-Mode header of one of following values Html, Bb, Text, SafeHtml | [optional]

### Return type

void (empty response body)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: text/plain, application/json, text/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
**204** |  |  -  |
**401** | User must be authenticated |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **v1_account_login_post**
> UserEnvelope v1_account_login_post()

Authenticate via credentials

### Example

```python
import time
import dm_api_account
from dm_api_account.api import login_api
from dm_api_account.model.bad_request_error import BadRequestError
from dm_api_account.model.general_error import GeneralError
from dm_api_account.model.login_credentials import LoginCredentials
from dm_api_account.model.user_envelope import UserEnvelope
from pprint import pprint
# Defining the host is optional and defaults to http://localhost
# See configuration.py for a list of all supported configuration parameters.
configuration = dm_api_account.Configuration(
    host = "http://localhost"
)


# Enter a context with an instance of the API client
with dm_api_account.ApiClient() as api_client:
    # Create an instance of the API class
    api_instance = login_api.LoginApi(api_client)
    x_dm_bb_render_mode = "X-Dm-Bb-Render-Mode_example" # str | Requests with user defined texts that allows usage of BB-codes may be rendered differently by passing the X-Dm-Bb-Render-Mode header of one of following values Html, Bb, Text, SafeHtml (optional)
    login_credentials = LoginCredentials(
        login="login_example",
        password="password_example",
        remember_me=True,
    ) # LoginCredentials | Login credentials (optional)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Authenticate via credentials
        api_response = api_instance.v1_account_login_post(x_dm_bb_render_mode=x_dm_bb_render_mode, login_credentials=login_credentials)
        pprint(api_response)
    except dm_api_account.ApiException as e:
        print("Exception when calling LoginApi->v1_account_login_post: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_dm_bb_render_mode** | **str**| Requests with user defined texts that allows usage of BB-codes may be rendered differently by passing the X-Dm-Bb-Render-Mode header of one of following values Html, Bb, Text, SafeHtml | [optional]
 **login_credentials** | [**LoginCredentials**](LoginCredentials.md)| Login credentials | [optional]

### Return type

[**UserEnvelope**](UserEnvelope.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json, text/json, application/*+json
 - **Accept**: text/plain, application/json, text/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** |  |  -  |
**400** | User not found or password is incorrect |  -  |
**403** | User is inactive or banned |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

