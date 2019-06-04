---
layout: post
title:  "Boucherie App - Authentication Pt. 1"
date:   2019-06-04 18:37:00 -0500
categories: projects
---

### Boucherie Festival App

Giving a status update of the application that I am currently working on the for the Boucherie Festival. This application will be used for the staff and vendors of the Boucherie Fest. The vendors will be able to pick out a booth location and give information about what they are offering. The staff, or the admins, will be able to log into their portal and approve/deny the vendors and make any notable changes to the Vendor's account (paid/unpaid).

### Adding Authentication with Identity Framework and Tokens

In order for us to have accounts, we need to first setup a way for people to sign up. We also need a way for the frontend of our application to communicate with the backend of our application for these users signing in. We start off by creating a controller for the Accounts. In this controller we want to use JSON Web Tokens (jwt) in order to generate a web token that can be used as an access token. For example, the token can show that the current user is logged in as an Admin and should have the Admin dashboard. Let's take a look at how we can accomplish this:

```csharp
        [HttpPost]
        public async Task<IActionResult> Register([FromBody] Credentials credentials)
        {
            var user = new IdentityUser { UserName = credentials.Email, Email = credentials.Email };

            var result = await userManager.CreateAsync(user, credentials.Password);

            if (!result.Succeeded)
            {
                return BadRequest(result.Errors);
            }

            await signInManager.SignInAsync(user, isPersistent: false);

            var jwt = new JwtSecurityToken();
            return Ok(new JwtSecurityTokenHandler().WriteToken(jwt));


        }
```
### Add Identity

In order for things like the user variable above to work we need to add Identity Framework to our startup.cs file:

```csharp
    services.AddIdentity<IdentityUser, IdentityRole>().AddEntityFrameworkStores<UserDbContext>();
```

What's great is that Identity has some built in requirements for things like passwords:

*Passwords must be at least 6 characters
*Passwords must have at least one lowercase ('a'-'z')
*Passwords must have at least one uppercase ('A'-'Z')
*Passwords must have at least one digit ('0'-'9')
*Passwords must have at least one non alphanumeric character


### Setting up the User Database

As seen above, with AddEntityFrameworkStores we need to pass in a context to a database. In our case, we setup a "UserDbContext".

```csharp
 public class UserDbContext : IdentityDbContext<IdentityUser>
    {
        public UserDbContext(DbContextOptions<UserDbContext> options) : base (options) { }
    }
```

### Until next time...

That was just a quick update, wanted to go over briefly what I have been working on the past few days. I have also setup the front end of the page as well, and will go in some more details with that as well, with a follow up post detailing how the two talk to each other!