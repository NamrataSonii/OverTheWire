# Natas Level 3 → Level 4

## Login Credentials

**Username:** `natas4`  
**URL:** `http://natas4.natas.labs.overthewire.org`

## Objective

Find the password for the next level, `natas5`.


After logging in, the page displays:

```text
Access disallowed. You are visiting from "" while authorized users should come only from "http://natas5.natas.labs.overthewire.org/"
```

This tells us that the server checks the **Referer** HTTP header.

## Step 1: Understand the Referer Header

The server expects the request to come from:

```text
http://natas5.natas.labs.overthewire.org/
```

Our current request does not contain the required Referer, so access is denied.

We need to modify the HTTP request and set the `Referer` header to the URL specified by the server.

## Step 2: Modify the Request Using Burp Suite

Open **Burp Suite** and configure the browser to send traffic through Burp.

Capture the request to the Natas Level 4 page.

In Burp, find the HTTP request and add or modify the following header:

```http
Referer: http://natas5.natas.labs.overthewire.org/
```

The request should contain:

```http
GET / HTTP/1.1
Host: natas4.natas.labs.overthewire.org
Referer: http://natas5.natas.labs.overthewire.org/
```

Send the modified request.

## Step 3: Get the Password

After setting the correct `Referer` header, the server accepts the request.

The page will display the password for the next level, `natas5`.

Copy that password.


## Key Concept

The server is using the HTTP `Referer` header as an access-control mechanism.

The important part of the request is:

```http
Referer: http://natas5.natas.labs.overthewire.org/
```

By modifying this header, we can satisfy the server's condition and access the page.
