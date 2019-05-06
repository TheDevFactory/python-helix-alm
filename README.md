# Using Pything with the REST API From Helix ALM (Perforce Software Inc)

Using python with the Helix ALM (TestTrack) REST API.




    Helper function. If an error is returned from the Helix ALM REST API via an HTTP response, this ensures the
    HALMResponse is properly initialized with the error values.

    Helix ALM REST API errors generally follow this structure:
        {
          "code": "Bad Request",
          "statusCode": 400,
          "message": "This is information why the request failed",
          "errorElementPath": "/path/to/the/parameter/object/that/failed"
        }

    :param dict error: - Error response from the Helix ALM REST API Server
    :param number status_code: Optional status code to set. If not specified, attempts to use the status code on
                                the error. If the passed-in error does not have a 'statusCode' property and there was
                                no previous status_code set on this object, the status_code defaults to 500.
