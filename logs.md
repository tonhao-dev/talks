---
theme: "white"
transition: "slide"
title: "Logs"
enableMenu: true
enableSearch: false
enableChalkboard: true
slideNumber: true
---

### Logs
I ❤️ Logs

_Luís Antônio (https://tonhao.dev)_

---


### Summary
  
- What is log
- Logs in distributed systems
- What should a log include?
- What should I log in my application?
- Best practices

---

<section data-background-color="antiquewhite">

### A little introduction
When you think about "data", what do you think?

</section>

---

<section data-background-color="antiquewhite">

### Probably something like this
![-](https://365datascience.com/resources/blog/2018-07-image6-min-10.png)

</section>

---

### But, in the real world
![-](https://media3.giphy.com/media/QsfwW8RbsZfCKhbaZX/giphy.gif)

---

<section data-background-color="antiquewhite">

### What do you think when someone speak "log"?

</section>

---

<section data-background-color="antiquewhite">

### Like this
![-](https://www.inmotionhosting.com/support/wp-content/uploads/2021/12/phpErrorLogging-02-1024x420.png)

</section>

---

<section data-background-color="antiquewhite">

### So in this context

- It is an append-only sequence of records ordered by time
- Records in the log are stored in the order they were appended.
- Reads proceed from left to right.
- Lets use the datetime as a key

</section>

---

<section data-background-color="antiquewhite">

### Visual
![-](https://media.discordapp.net/attachments/1118725310582628413/1182164656027082793/wf9yOX21XJBQgAAAABJRU5ErkJggg.png?ex=6583b3a1&is=65713ea1&hm=bd81cb0136ca6abc617dbc381a3913277ec6001fca756b574897b67ae8d94992&=&format=webp&quality=lossless&width=569&height=135)

</section>

---

<section data-background-color="antiquewhite">

### By definition
A log is a chronological record that captures and stores a sequence of events.

</section>

---

<section data-background-color="antiquewhite">

### Principal Uses

- pub/sub mechanism to transmit data to other replicas
- consistency to order the updates that will be applied between replicas

</section>

---

<section data-background-color="aquamarine">

### Logs in Distributed System 

_"If two identical, deterministic processes begin in the same state and get the same inputs in the same order, they will produce the same output and end in the same state."_

</section>

---

<section data-background-color="aquamarine">

### Variety of Log-Centric Designs
State machine Replication vs Primary Backup 

</section>

---

<section data-background-color="aquamarine">

### State Machine Replication
![-](https://files.speakerdeck.com/presentations/f413c13066dd418388fd9a7a05b19c3e/slide_10.jpg){width=70%}

</section>

---

<section data-background-color="aquamarine">

### Primary Backup
![-](https://media.discordapp.net/attachments/1118725310582628413/1182171054278455408/wMOOlnof2mhuwAAAABJRU5ErkJggg.png?ex=6583b997&is=65714497&hm=c622e59c7512759760b3503309c724a518a98c7a6acf9a93709eefe0c7e685c8&=&format=webp&quality=lossless&width=569&height=470)

</section>

---

<section data-background-color="aquamarine">

### Example
We have a remote web service based on HTTP will respond to the following commands:

    x?   // get the current value of x
    x+=5 // add 5 to x
    x-=2 // subtract 2 from x
    y*=2 // double y

</section>

---

<section data-background-color="aquamarine">

### Whats happen on State Machine Replication?

</section>

---

<section data-background-color="aquamarine">

### Whats happen on Primary Backup?

</section>

---

<section data-background-color="aquamarine">

### Ok, some question at here?

</section>

---

<section data-background-color="lightgray">

### What should a log include?

- Event data records things that happen rather than things that are.
- In web systems, this means user activity logging.
</section>

---

<section data-background-color="lightgray">

### 5W's (#medo)
1. Who
2. What
3. When
4. Where
5. Why

</section>

---

<section data-background-color="lightgray">

### Who
1. User ID
2. Machine ID
3. Process ID
4. Unique Cookie
5. IP Address

</section>

---

<section data-background-color="lightgray">

### What
1. Message
2. Model/Entitiiy Id
3. Exception (StandardError)
4. Event

</section>

---

<section data-background-color="lightgray">

### When
1. Timestamp

</section>

---

<section data-background-color="lightgray">

### Where
1. Stacktrace
2. Request ID
3. Machine ID
4. Process Id
5. Job/Worker UID

</section>

---

<section data-background-color="lightgray">

### Why
1. Is Aggragatable? 
2. Is it searchable?
3. Is it analyzable?

</section>

---

<section data-background-color="lightgray">

### So, what do you include on your logs?

</section>

---

<section data-background-color="gold">

### What should I log in my application?

</section>

---

<section data-background-color="gold">

### Application Session start/stop
1. When the application start/stop
2. Include additional messages at the start and end of these sections.

</section>

---

<section data-background-color="gold">

### User Session start/stop
1.Log distinctive messages at the start and end of each of these logical sessions.

</section>

---

<section data-background-color="gold">

### Unhandled Exceptions
1. Passing the exception object as well as what context you have.

</section>

---

<section data-background-color="gold">

### Handled Exceptions
1. Where an exception is consumed within a catch block that you log the exception with an Informational severity

</section>

---

<section data-background-color="gold">

### Process Entrance and Exit
1. Incoming requests
2. Database query
3. Web service

</section>

---

<section data-background-color="gold">

### Significant User Actions
1. Button actions
2. Navigating to a new context
3. Any message box / modal prompt displayed.
4. Expensive operations

</section>

---

<section data-background-color="gold">

### Display Help requests

</section>

---

<section data-background-color="gold">

### Cancelled Actions

</section>

---

<section data-background-color="paleturquoise">

### What Not to Log

</section>

---

<section data-background-color="paleturquoise">

### Avoid logging simple routine actions

</section>

---

<section data-background-color="paleturquoise">

### Avoid logging in tight loops

</section>

---

<section data-background-color="paleturquoise">

### Think carefully about sensitive information

</section>

---

<section data-background-color="teal">

### Best practices

</section>

---

<section data-background-color="teal">

### Message Priorities/Levels
- fatal
- error
- warn 
- info 
- debug
- trace

</section>

---

<section data-background-color="teal">

### Use logging formats that are easy to understand

    ### Example of an NGINX access log that is difficult to parse:
    127.180.71.3 - - [10/May/2022:08:05:32 +0000] "GET /downloads/product_1 HTTP/1.1" 304 0 "-" "Debian APT-HTTP/1.3 (0.8.16~exp12ubuntu10.21)"


    ### Example of the same log information in a parsable log format:
    {
      "remote_addr":"93.180.71.3",
      "time":"1586514731",
      "method":"GET",
      "path":"/downloads/product_1",
      "version":"HTTP/1.1",
    }

</section>

---

<section data-background-color="teal">

### Don’t log large messages!
Logging costs money.

</section>

---

<section data-background-color="teal">

### Don’t Write Logs by Yourself

</section>

---

<section data-background-color="teal">

### Add Context to Your Log Messages

    // instead of this
    Transaction failed

    // make this
    Transaction 2346432 failed: cc number checksum incorrect

</section>

---

### Conclusion
In conclusion logs offering invaluable insights into its behavior, health, and performance.

---

### I ❤️ Logs

Luís Antônio (https://tonhao.dev)
