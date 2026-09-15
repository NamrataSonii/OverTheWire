# Natas Level 2 → Level 3

## Login Credentials

**Username:** `natas3`  
**URL:** `http://natas3.natas.labs.overthewire.org`

## Objective

Find the password for the next level, `natas4`.

## Step 1: Inspect the Source Code

After logging in, view the source code of the webpage using:

```text
Ctrl + U
```

In the source code, we find the following comment:

```html
<!-- No more information leaks!! Not even Google will find it this time... -->
```

This suggests that we should look for information that search engines such as Google might normally find.

## Step 2: Check `robots.txt`

Websites commonly use a file called `robots.txt` to tell search engine crawlers which directories or files they should not access.

Open:

```text
http://natas3.natas.labs.overthewire.org/robots.txt
```

Inside `robots.txt`, we find:

```text
User-agent: *
Disallow: /s3cr3t/
```

This reveals the hidden `/s3cr3t/` directory.

## Step 3: Open the Hidden Directory

Since we now know that `/s3cr3t/` exists, add it to the URL:

```text
http://natas3.natas.labs.overthewire.org/s3cr3t/
```

Open the directory and look for the available files.

## Step 4: Find the Password

Inside the `/s3cr3t/` directory, we find a file containing the password for the next level.

Open the file and copy the password.

