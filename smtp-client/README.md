# SMTP Client

Exercise: incrementally create an SMTP client.

## Test server

To test the SMTP client, run a test server as follows:
```
$ docker-compose up
```

Once the server is running, connections can be established to TCP port 2500. Also, a web UI is accessible in port 1080.

## Roadmap

  1. Implement a simple script that allows sending a fixed email to the test server, and verify that it appears in the web UI.
  1. Based on that script, build a higher level API that allows sending plain text emails abstracting away protocol details.
  1. Add support for HTML messages.
  1. Add support for attachments.
  1. Package the SMTP client in a [shard](http://crystalshards.xyz/) so it can be distributed and used by other people.


## Example

The following example shows the messages that need to be exchanged between the client and a server to send a simple plain text message [[source](http://www.anta.net/misc/telnet-troubleshooting/smtp.shtml)]:

```
$ telnet localhost 2500
...
Connected to localhost
Escape character is '^]'.
> 220 localhost ESMTP
HELO localhost
> 250 localhost
MAIL from: <sender@example.com>
> 250 Accepted
RCPT to: <recipient@example.com>
> 250 Accepted
DATA
> 354 End data with <CR><LF>.<CR><LF>
From: sender@example.com
To: recipient@example.com
Subject: Test message

This is a test message.
.
> 250 Message queued as tMoQ9P15
QUIT
```
