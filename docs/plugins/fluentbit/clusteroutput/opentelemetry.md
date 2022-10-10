# OpenTelemetry

The OpenTelemetry plugin allows you to take metrics from Fluent Bit and submit them to an OpenTelemetry HTTP endpoint.

>Note: At the moment only HTTP endpoints are supported.


| Field              | Description                                                                                                                                                                                                                                                                                                                  | Scheme                          |
|--------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------|
| host               | IP address or hostname of the target HTTP Server.                                                                                                                                                                                                                                                                            | string                          |
| port               | TCP port of the target HTTP Server.                                                                                                                                                                                                                                                                                          | *int32                          |
| httpUser           | Optional username credential for access.                                                                                                                                                                                                                                                                                     | *[plugins.Secret](../secret.md) |
| httpPassword       | Password for user defined in HTTP_User.                                                                                                                                                                                                                                                                                      | *[plugins.Secret](../secret.md) |
| proxy              | Specify an HTTP Proxy. The expected format of this value is http://HOST:PORT. Note that HTTPS is not currently supported. It is recommended not to set this and to configure the [HTTP proxy environment variables](https://docs.fluentbit.io/manual/administration/http-proxy) instead as they support both HTTP and HTTPS. | string                          |
| uri                | Specify an optional HTTP URI for the target web server, e.g: /something.                                                                                                                                                                                                                                                     | string                          |
| header             | Add a HTTP header key/value pair. Multiple headers can be set.                                                                                                                                                                                                                                                               | map[string]string               |
| logResponsePayload | Log the response payload within the Fluent Bit log.                                                                                                                                                                                                                                                                          | *bool                           |
| addLabel           | This allows you to add custom labels to all metrics exposed through the OpenTelemetry exporter. You may have multiple of these fields.                                                                                                                                                                                       | map[string]string               |
| tls                |                                                                                                                                                                                                                                                                                                                              | *[plugins.TLS](../tls.md)       |