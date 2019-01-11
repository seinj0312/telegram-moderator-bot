# User's Guide

## Telegram Moderator Bot
This Telegram Moderator Bot is capable of adding moderators to Telegram supergroups.
Regular groups and channels are not supported.

### How to set it up
1. Talk to the @BotFather and create a bot on Telegram.
1. Deploy the using the tutorial at [README.md](README.md)
1. Invite your bot to your Telegram supergroup.
1. Make your bot Full Administrator on the supergroup. It looks like this:
![admin](resources/admin.png)

## Moderators
Moderators are supergroup administrators with some modified privileges. Moderators can **delete a message**
and **pin a message** using the built-in GUI functionality. No other usual admin functions are necessary
(or encouraged) for moderators. It is explicitly forbidden to give a moderator the
"Ban users" and "Add new Admins" privileges. These privileges would allow them to have power over other moderators.

Apart from the mentioned administrative privileges, moderators can issue the `/ban @username` command to the Telegram Bot
to ban a regular member of the supergroup. Moderators can unban users using the `/unban @username` command.
(The user has to rejoin the group after unbanning.)

Moderators can write up a user with the `/warn @username` command. After two warnings the user gets banned.

## (Full) Administrators
Administrators have more privileges than moderators. For the Telegram bot, any administrator with the "Add new Admins"
privilege is considered a "Full" administrator. The creator of the supergroup is also considered a Full administrator.
Full administrators can issue the `/promote @username` and `/demote @username` commands to appoint new moderators
or remove current moderators.

## Restrictions
The bot will only "know" a user if the user has sent at least one message on the supergroup.

This means that to promote a user to moderator status, the user has to at least say "Hi" on the supergroup.

## List of commands for moderators (and administrators)

```
/hello
```
A nice welcome message. It only works if you're a moderator or administrator so you can check your privileges.

```
/list
```
Lists moderators.

```
/warn @username
```
Issues a warning for the user. After two warnings the bot bans the user.

Multiple names can be added using space as a separator.

```
/ban @username
```
Ban a user. Use the GUI to quickly pinpoint the user and fill in the right username.
Administrators and other moderators cannot be banned.

Multiple names can be added using space as a separator.

```
/unban @username
```
Removes the user from the banned list and resets its warning counter.
Does not add the user back in the supergroup.

Multiple names can be added using space as a separator.

## List of commands for administrators only

```
/promote @username
```
Give a regular user moderator privileges. Current moderators and administrators will be unaffected.

Multiple names can be added using space as a separator.

```
/demote @username
```
Take away administrative privileges from a moderator. The creator user or full administrators
(administrators with the "Add new Admins" privilege) will be unaffected.

Multiple names can be added using space as a separator.
