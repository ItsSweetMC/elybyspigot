![logo111](https://github.com/user-attachments/assets/ff7cee43-4cf9-4443-b6b0-f5c961305aae)

---

# ElyBySpigot

**A Spigot fork that uses Ely.by authentication instead of Mojang's system.**

---

## Overview

ElyBySpigot replaces Mojang's official authentication library with Ely.by's custom **authlib**, enabling players with Ely.by accounts to authenticate securely on your server while maintaining online mode functionality.

---

## How It Works

ElyBySpigot interacts with Ely.by's services to authenticate users. Below are some key API endpoints used:

> **UUID by Username**  
Retrieve the UUID associated with a given username.

- **Request:**
  ```http
  GET /api/users/profiles/minecraft/{username}
  ```
- **Response:**
  ```json
  {
    "id": "ffc8fdc95824509e8a57c99b940fb996",
    "name": "ErickSkrauch"
  }
  ```

> **Username History by UUID**  
Retrieve all usernames associated with a specific UUID.

- **Request:**
  ```http
  GET /api/user/profiles/{uuid}/names
  ```
- **Response:**
  ```json
  [
    {
      "name": "Admin"
    },
    {
      "name": "ErickSkrauch",
      "changedToAt": 1440707723000
    }
  ]
  ```

For more details, refer to the [Ely.by API Documentation](https://docs.ely.by/en/api.html).

---

## Drawbacks

- **Mojang Authentication Unsupported:** Players cannot log in using Mojang accounts.  
- **Exclusive Ely.by Authlib Usage:** Authentication is managed solely through Ely.by's official **authlib**.

---

## Installation Guide

To set up ElyBySpigot on your server:

1. **Install Ely.by Authlib**  
   Follow the official guide:  
   [Ely.by Authlib Installation](https://docs.ely.by/en/minecraft-auth.html#install-server)

2. **Update Your Server Configuration**  
   - Replace the default `authlib` in your Spigot server with the Ely.by version.  
   - Configure your server to run in online mode to support Ely.by authentication.

---

## Features

- **Custom Authentication:** Supports Ely.by accounts for secure login.  
- **Secure Online Mode:** Provides online mode functionality for Ely.by users.  
- **Spigot Compatibility:** Operates just like traditional Spigot, with minimal modifications.  

---

## Debugging and Support

If you encounter any issues, watch this video where I troubleshoot bugs:  
[Debugging ElyBySpigot](https://youtu.be/f3N10ql_BEM)

---
