# Natas Level 4 → Level 5

**Username:** `natas5`

**URL:** `http://natas5.natas.labs.overthewire.org`

## Objective

Find the password for the next level, `natas6`.

## Problem

After logging in, the page shows:

`Access disallowed. You are not logged in`

The application uses a cookie:

`loggedin=0`

## Solution Using Burp Suite

1. Turn **FoxyProxy → Burp** ON.
2. Open the Natas 5 URL in Edge and log in.
3. Open **Burp Suite → Proxy → HTTP history**.
4. Find the request to `natas5.natas.labs.overthewire.org`.
5. Right-click the request → **Send to Repeater**.
6. Open **Repeater**.
7. Find:

`Cookie: loggedin=0`

8. Change it to:

`Cookie: loggedin=1`

The request should contain:

`GET / HTTP/1.1`
`Host: natas5.natas.labs.overthewire.org`
`Cookie: loggedin=1`

9. Click **Send**.
10. The response should contain the password for **natas6**.

## Key Concept

The server is using the client-controlled `loggedin` cookie to determine whether the user is logged in.

to:

`loggedin=1`

Then send the modified request using Burp Repeater.
