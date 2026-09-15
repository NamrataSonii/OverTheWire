# Natas Level 1 → Level 2

## Login Credentials

**Username:** `natas2`  
**URL:** `http://natas2.natas.labs.overthewire.org`

## Objective

Find the password for the next level, `natas3`.

## Step 1: Inspect the Source Code

After logging in, view the source code of the webpage using:

```text
Ctrl + U
```

In the source code, we find:

```html
<img src="files/pixel.png">
```

This tells us that a `files` directory exists on the server.

## Step 2: Open the `files` Directory

Since we know the `files` directory exists, add `/files` to the URL:

```text
http://natas2.natas.labs.overthewire.org/files
```

Inside the directory, we find:

```text
users.txt
```

Click on `users.txt` to open the file.

## Step 3: Find the Password for `natas3`

After opening `users.txt`, we can see the usernames and passwords stored in the file.

Find the username `natas3` and copy the password next to it.

This password will be used to log in to the next level.

