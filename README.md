# java-web-gradle-spring-jsp-challenge-question-des-encryption-bcrypt-encode

## Description
A springboot secure web app with jsp support.
Three roles are defined; USER, ADMIN, and SUPER. All roles
can access pages `/home`, `/login`, and `/about`. Only USER
can access `/user` and ADMIN only `/admin` whereas SUPER can
navigate to either and have its own `/super`. Each role
has an action USER=VIEW ONLY, ADMIN=READ/WRITE, SUPER=CREATE.
All password are encrypted with DES and encoded with bcrypt
to insure strong passwords.

DES is a 48 bit encryption considered by most too weak
for passwords. It is usually used for checksums and other
tamper proof verification.

Presents a register form to create an inMemoryUser.
Once the user is created it is given the `USER` role
by default and auto logged in.

Presents a reset form to reset passwords on any user,
by default the user is reassigned `USER` role and auto
logged in. Only restriction on passwords are they match;
all validation is done client side.

Uses a challenge question on password rest and user register
to verify user. Customizes user data class by extending the
UserDetailService.

## Tech stack
- java
- gradle

## Docker stack
- gradle:jdk11

## To run
`sudo ./install.sh -u`
Available at http://localhost
- Login with id: user and password: pass
  - Challenge: question="Year you were born?" answer=1900
- Login with id: admin and password: pass
  - Challenge: question=0 answer=1900
- Login with id: super and password: pass
  - Challenge: question=0 answer=1900

## To stop (optional)
`sudo ./install.sh -d`

## For help
`sudo ./install.sh -h`

## Credits
- https://hellokoding.com/spring-security-login-logout-jsp/
- https://www.javainterviewpoint.com/spring-security-inmemoryuserdetailsmanager/
