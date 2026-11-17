### what is http request smuggling ?

HTTP Request Smuggling is a vulnerability that occurs when multiple servers in an HTTP request chain, such as a front-end server and a back-end server, interpret the boundaries of an HTTP request differently.

This often happens when the servers use different mechanisms, such as `Content-Length` and `Transfer-Encoding`, to determine where the request body ends.

As a result, part of a request may be interpreted as a separate request by one of the servers, potentially allowing an attacker to interfere with subsequent requests
### The Root Cause 

The root cause of HTTP Request Smuggling is a disagreement between the front-end and back-end servers about where an HTTP request ends.

This can happen when they use different mechanisms to determine the end of the request body:

- **Content-Length:** Specifies the length of the request body in bytes.
    
- **Transfer-Encoding: chunked:** Encodes the request body in chunks. Each chunk starts with its size in hexadecimal, and a zero-size chunk indicates the end of the chunked body.
### How It Works

The attacker crafts a malicious HTTP request that is interpreted differently by the front-end and back-end servers.

As a result, the back-end may interpret part of the request body as the beginning of a subsequent request. This can interfere with how the application processes subsequent requests and may lead to serious security consequences.   

### Detection

HTTP Request Smuggling can be detected by testing how the front-end and back-end servers interpret HTTP request boundaries.

Common detection methods include:

- **Timing-based detection:** Send specially crafted requests and observe whether the server response is delayed, which may indicate that the back-end is waiting for more data.
    
- **Differential response testing:** Compare how the server responds to requests with different `Content-Length` and `Transfer-Encoding` headers.
    
- **Request boundary testing:** Check whether the front-end and back-end disagree about where the request body ends.
    
- **Burp Suite:** Use Burp Repeater to manually test request handling and analyze the responses. Burp Suite's HTTP Request Smuggler extension can also help automate detection.
    

A single unusual response or timeout does not prove the vulnerability. Repeat tests carefully and confirm the behavior using a controlled test case.

### Prevention

HTTP Request Smuggling can be prevented or mitigated by ensuring that the front-end and back-end servers handle HTTP requests consistently.

- **Consistent HTTP parsing:** Ensure that all servers agree on the boundaries of HTTP requests.
    
- **Reject ambiguous requests:** Reject requests containing conflicting or invalid `Content-Length` and `Transfer-Encoding` headers.
    
- **Use secure configurations:** Configure reverse proxies and back-end servers to handle HTTP requests securely and consistently.
    
- **Keep software updated:** Apply security patches to web servers, proxies, and other HTTP infrastructure.
    
- **Avoid unsafe connection reuse:** Ensure that connections are not reused when a request has been parsed incorrectly or leaves unexpected data unread.
    

The main goal is to e

### Type

- CL.TE: the front-end server uses the `Content-Length` header and the back-end server uses the `Transfer-Encoding` header.

- TE.CL: the front-end server uses the `Transfer-Encoding` header and the back-end server uses the `Content-Length` header.

- TE.TE: the front-end and back-end servers both support the `Transfer-Encoding` header, but one of the servers can be induced not to process it by obfuscating the header in some way.