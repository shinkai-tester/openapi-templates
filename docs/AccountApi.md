# dm_api_account.AccountApi

All URIs are relative to *http://localhost*

Method | HTTP request | Description
------------- | ------------- | -------------
[**activate**](AccountApi.md#activate) | **PUT** /v1/account/{token} | Activate registered user
[**change_email**](AccountApi.md#change_email) | **PUT** /v1/account/email | Change registered user email
[**change_password**](AccountApi.md#change_password) | **PUT** /v1/account/password | Change registered user password
[**get_current**](AccountApi.md#get_current) | **GET** /v1/account | Get current user
[**register**](AccountApi.md#register) | **POST** /v1/account | Register new user
[**reset_password**](AccountApi.md#reset_password) | **POST** /v1/account/password | Reset registered user password


# **activate**
> UserEnvelope activate(token)

Activate registered user

### Example

```python
import time
import dm_api_account
from dm_api_account.api import account_api
from dm_api_account.model.general_error import GeneralError
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
    api_instance = account_api.AccountApi(api_client)
    token = "token_example" # str | Activation token
    x_dm_auth_token = "X-Dm-Auth-Token_example" # str | Authenticated requests require X-Dm-Auth-Token header. You can get the data from POST /account/ method, sending login and password in \"token\" response field (optional)
    x_dm_bb_render_mode = "X-Dm-Bb-Render-Mode_example" # str | Requests with user defined texts that allows usage of BB-codes may be rendered differently by passing the X-Dm-Bb-Render-Mode header of one of following values Html, Bb, Text, SafeHtml (optional)

    # example passing only required values which don't have defaults set
    try:
        # Activate registered user
        api_response = api_instance.activate(token)
        pprint(api_response)
    except dm_api_account.ApiException as e:
        print("Exception when calling AccountApi->activate: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Activate registered user
        api_response = api_instance.activate(token, x_dm_auth_token=x_dm_auth_token, x_dm_bb_render_mode=x_dm_bb_render_mode)
        pprint(api_response)
    except dm_api_account.ApiException as e:
        print("Exception when calling AccountApi->activate: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **token** | **str**| Activation token |
 **x_dm_auth_token** | **str**| Authenticated requests require X-Dm-Auth-Token header. You can get the data from POST /account/ method, sending login and password in \&quot;token\&quot; response field | [optional]
 **x_dm_bb_render_mode** | **str**| Requests with user defined texts that allows usage of BB-codes may be rendered differently by passing the X-Dm-Bb-Render-Mode header of one of following values Html, Bb, Text, SafeHtml | [optional]

### Return type

[**UserEnvelope**](UserEnvelope.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: text/plain, application/json, text/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | User has been activated and logged in |  -  |
**400** | Token is invalid |  -  |
**410** | Token is expired |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **change_email**
> UserEnvelope change_email()

Change registered user email

### Example

```python
import time
import dm_api_account
from dm_api_account.api import account_api
from dm_api_account.model.bad_request_error import BadRequestError
from dm_api_account.model.user_envelope import UserEnvelope
from dm_api_account.model.change_email import ChangeEmail
from pprint import pprint
# Defining the host is optional and defaults to http://localhost
# See configuration.py for a list of all supported configuration parameters.
configuration = dm_api_account.Configuration(
    host = "http://localhost"
)


# Enter a context with an instance of the API client
with dm_api_account.ApiClient() as api_client:
    # Create an instance of the API class
    api_instance = account_api.AccountApi(api_client)
    x_dm_auth_token = "X-Dm-Auth-Token_example" # str | Authenticated requests require X-Dm-Auth-Token header. You can get the data from POST /account/ method, sending login and password in \"token\" response field (optional)
    x_dm_bb_render_mode = "X-Dm-Bb-Render-Mode_example" # str | Requests with user defined texts that allows usage of BB-codes may be rendered differently by passing the X-Dm-Bb-Render-Mode header of one of following values Html, Bb, Text, SafeHtml (optional)
    change_email = ChangeEmail(
        login="login_example",
        password="password_example",
        email="email_example",
    ) # ChangeEmail |  (optional)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Change registered user email
        api_response = api_instance.change_email(x_dm_auth_token=x_dm_auth_token, x_dm_bb_render_mode=x_dm_bb_render_mode, change_email=change_email)
        pprint(api_response)
    except dm_api_account.ApiException as e:
        print("Exception when calling AccountApi->change_email: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_dm_auth_token** | **str**| Authenticated requests require X-Dm-Auth-Token header. You can get the data from POST /account/ method, sending login and password in \&quot;token\&quot; response field | [optional]
 **x_dm_bb_render_mode** | **str**| Requests with user defined texts that allows usage of BB-codes may be rendered differently by passing the X-Dm-Bb-Render-Mode header of one of following values Html, Bb, Text, SafeHtml | [optional]
 **change_email** | [**ChangeEmail**](ChangeEmail.md)|  | [optional]

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
**200** | Email has been changed |  -  |
**400** | Some account details were incorrect |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **change_password**
> UserEnvelope change_password()

Change registered user password

### Example

```python
import time
import dm_api_account
from dm_api_account.api import account_api
from dm_api_account.model.bad_request_error import BadRequestError
from dm_api_account.model.change_password import ChangePassword
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
    api_instance = account_api.AccountApi(api_client)
    x_dm_auth_token = "X-Dm-Auth-Token_example" # str | Authenticated requests require X-Dm-Auth-Token header. You can get the data from POST /account/ method, sending login and password in \"token\" response field (optional)
    x_dm_bb_render_mode = "X-Dm-Bb-Render-Mode_example" # str | Requests with user defined texts that allows usage of BB-codes may be rendered differently by passing the X-Dm-Bb-Render-Mode header of one of following values Html, Bb, Text, SafeHtml (optional)
    change_password = ChangePassword(
        login="login_example",
        token="token_example",
        old_password="old_password_example",
        new_password="new_password_example",
    ) # ChangePassword |  (optional)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Change registered user password
        api_response = api_instance.change_password(x_dm_auth_token=x_dm_auth_token, x_dm_bb_render_mode=x_dm_bb_render_mode, change_password=change_password)
        pprint(api_response)
    except dm_api_account.ApiException as e:
        print("Exception when calling AccountApi->change_password: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_dm_auth_token** | **str**| Authenticated requests require X-Dm-Auth-Token header. You can get the data from POST /account/ method, sending login and password in \&quot;token\&quot; response field | [optional]
 **x_dm_bb_render_mode** | **str**| Requests with user defined texts that allows usage of BB-codes may be rendered differently by passing the X-Dm-Bb-Render-Mode header of one of following values Html, Bb, Text, SafeHtml | [optional]
 **change_password** | [**ChangePassword**](ChangePassword.md)|  | [optional]

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
**200** | Password has been changed |  -  |
**400** | Some account details were incorrect |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_current**
> UserDetailsEnvelope get_current(x_dm_auth_token)

Get current user

### Example

```python
import time
import dm_api_account
from dm_api_account.api import account_api
from dm_api_account.model.user_details_envelope import UserDetailsEnvelope
from pprint import pprint
# Defining the host is optional and defaults to http://localhost
# See configuration.py for a list of all supported configuration parameters.
configuration = dm_api_account.Configuration(
    host = "http://localhost"
)


# Enter a context with an instance of the API client
with dm_api_account.ApiClient() as api_client:
    # Create an instance of the API class
    api_instance = account_api.AccountApi(api_client)
    x_dm_auth_token = "X-Dm-Auth-Token_example" # str | Authenticated requests require X-Dm-Auth-Token header. You can get the data from POST /account/ method, sending login and password in \"token\" response field
    x_dm_bb_render_mode = "X-Dm-Bb-Render-Mode_example" # str | Requests with user defined texts that allows usage of BB-codes may be rendered differently by passing the X-Dm-Bb-Render-Mode header of one of following values Html, Bb, Text, SafeHtml (optional)

    # example passing only required values which don't have defaults set
    try:
        # Get current user
        api_response = api_instance.get_current(x_dm_auth_token)
        pprint(api_response)
    except dm_api_account.ApiException as e:
        print("Exception when calling AccountApi->get_current: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Get current user
        api_response = api_instance.get_current(x_dm_auth_token, x_dm_bb_render_mode=x_dm_bb_render_mode)
        pprint(api_response)
    except dm_api_account.ApiException as e:
        print("Exception when calling AccountApi->get_current: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_dm_auth_token** | **str**| Authenticated requests require X-Dm-Auth-Token header. You can get the data from POST /account/ method, sending login and password in \&quot;token\&quot; response field |
 **x_dm_bb_render_mode** | **str**| Requests with user defined texts that allows usage of BB-codes may be rendered differently by passing the X-Dm-Bb-Render-Mode header of one of following values Html, Bb, Text, SafeHtml | [optional]

### Return type

[**UserDetailsEnvelope**](UserDetailsEnvelope.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: text/plain, application/json, text/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** |  |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **register**
> register()

Register new user

### Example

```python
import time
import dm_api_account
from dm_api_account.api import account_api
from dm_api_account.model.bad_request_error import BadRequestError
from dm_api_account.model.registration import Registration
from pprint import pprint
# Defining the host is optional and defaults to http://localhost
# See configuration.py for a list of all supported configuration parameters.
configuration = dm_api_account.Configuration(
    host = "http://localhost"
)


# Enter a context with an instance of the API client
with dm_api_account.ApiClient() as api_client:
    # Create an instance of the API class
    api_instance = account_api.AccountApi(api_client)
    x_dm_auth_token = "X-Dm-Auth-Token_example" # str | Authenticated requests require X-Dm-Auth-Token header. You can get the data from POST /account/ method, sending login and password in \"token\" response field (optional)
    x_dm_bb_render_mode = "X-Dm-Bb-Render-Mode_example" # str | Requests with user defined texts that allows usage of BB-codes may be rendered differently by passing the X-Dm-Bb-Render-Mode header of one of following values Html, Bb, Text, SafeHtml (optional)
    registration = Registration(
        login="login_example",
        email="email_example",
        password="password_example",
    ) # Registration | New user credentials information (optional)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Register new user
        api_instance.register(x_dm_auth_token=x_dm_auth_token, x_dm_bb_render_mode=x_dm_bb_render_mode, registration=registration)
    except dm_api_account.ApiException as e:
        print("Exception when calling AccountApi->register: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_dm_auth_token** | **str**| Authenticated requests require X-Dm-Auth-Token header. You can get the data from POST /account/ method, sending login and password in \&quot;token\&quot; response field | [optional]
 **x_dm_bb_render_mode** | **str**| Requests with user defined texts that allows usage of BB-codes may be rendered differently by passing the X-Dm-Bb-Render-Mode header of one of following values Html, Bb, Text, SafeHtml | [optional]
 **registration** | [**Registration**](Registration.md)| New user credentials information | [optional]

### Return type

void (empty response body)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json, text/json, application/*+json
 - **Accept**: text/plain, application/json, text/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
**201** | User has been registered and expects confirmation by e-mail |  -  |
**400** | Some of registration properties were invalid |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **reset_password**
> reset_password()

Reset registered user password

### Example

```python
import time
import dm_api_account
from dm_api_account.api import account_api
from dm_api_account.model.bad_request_error import BadRequestError
from dm_api_account.model.reset_password import ResetPassword
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
    api_instance = account_api.AccountApi(api_client)
    x_dm_auth_token = "X-Dm-Auth-Token_example" # str | Authenticated requests require X-Dm-Auth-Token header. You can get the data from POST /account/ method, sending login and password in \"token\" response field (optional)
    x_dm_bb_render_mode = "X-Dm-Bb-Render-Mode_example" # str | Requests with user defined texts that allows usage of BB-codes may be rendered differently by passing the X-Dm-Bb-Render-Mode header of one of following values Html, Bb, Text, SafeHtml (optional)
    reset_password = ResetPassword(
        login="login_example",
        email="email_example",
    ) # ResetPassword | Account details (optional)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Reset registered user password
        api_instance.reset_password(x_dm_auth_token=x_dm_auth_token, x_dm_bb_render_mode=x_dm_bb_render_mode, reset_password=reset_password)
    except dm_api_account.ApiException as e:
        print("Exception when calling AccountApi->reset_password: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_dm_auth_token** | **str**| Authenticated requests require X-Dm-Auth-Token header. You can get the data from POST /account/ method, sending login and password in \&quot;token\&quot; response field | [optional]
 **x_dm_bb_render_mode** | **str**| Requests with user defined texts that allows usage of BB-codes may be rendered differently by passing the X-Dm-Bb-Render-Mode header of one of following values Html, Bb, Text, SafeHtml | [optional]
 **reset_password** | [**ResetPassword**](ResetPassword.md)| Account details | [optional]

### Return type

void (empty response body)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json, text/json, application/*+json
 - **Accept**: text/plain, application/json, text/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
**201** | Created |  -  |
**400** | Some account details were incorrect |  -  |
**200** | Password has been reset |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

