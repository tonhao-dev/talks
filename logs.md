---
theme: "white"
transition: "fade"
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

<section data-background-color="aquamarine">
  <h2>Summary</h2>
  <ol>
    <li>What is log</li>
    <li>Logs in distributed systems</li>
    <li>What should a log include?</li>
    <li>What should I log in my application?</li>
    <li>Best practices</li>
  </ol>
</section>



---

<section data-background-color="red">

### What do you think when someone speak "log"? (color)

</section>

---

### Like this
![-](https://www.inmotionhosting.com/support/wp-content/uploads/2021/12/phpErrorLogging-02-1024x420.png)

---

### So in this context

- It is an append-only sequence of records ordered by time
- Records in the log are stored in the order they were appended.
- Reads proceed from left to right.
- Lets use the datetime as a key

---

### Visual
![-](https://media.discordapp.net/attachments/1118725310582628413/1182164656027082793/wf9yOX21XJBQgAAAABJRU5ErkJggg.png?ex=6583b3a1&is=65713ea1&hm=bd81cb0136ca6abc617dbc381a3913277ec6001fca756b574897b67ae8d94992&=&format=webp&quality=lossless&width=569&height=135)

---

### Principal Uses

- pub/sub mechanism to transmit data to other replicas
- consistency to order the updates that will be applied between replicas

---

### Logs in Distributed System (color)

_"If two identical, deterministic processes begin in the same state and get the same inputs in the same order, they will produce the same output and end in the same state."_

---

### Variety of Log-Centric Designs

State machine Replication vs Primary Backup 

---

### State Machine Replication
![-](https://files.speakerdeck.com/presentations/f413c13066dd418388fd9a7a05b19c3e/slide_10.jpg){width=70%}

---

### Primary Backup
![-](https://media.discordapp.net/attachments/1118725310582628413/1182171054278455408/wMOOlnof2mhuwAAAABJRU5ErkJggg.png?ex=6583b997&is=65714497&hm=c622e59c7512759760b3503309c724a518a98c7a6acf9a93709eefe0c7e685c8&=&format=webp&quality=lossless&width=569&height=470)

---

### Example
We have a remote web service based on HTTP will respond to the following commands:

    x?   // get the current value of x
    x+=5 // add 5 to x
    x-=2 // subtract 2 from x
    y*=2 // double y

---

### Whats happen on State Machine Replication?

---

### Whats happen on Primary Backup?

---

### Ok, some question at here?

---

### What should a log include? (color)
- Event data records things that happen rather than things that are.
- In web systems, this means user activity logging.

---

### 5W's (#medo)
1. Who
2. What
3. When
4. Where
5. Why

---

### Who
1. User ID
2. Machine ID
3. Process ID
4. Unique Cookie
5. IP Address

---

### What
1. Message
2. Model/Entitiiy Id
3. Exception (StandardError)
4. Event

---

### When
1. Timestamp

---

### Where
1. Stacktrace
2. Request ID
3. Machine ID
4. Process Id
5. Job/Worker UID

---

### Why
1. Is Aggragatable? 
2. Is it searchable?
3. Is it analyzable?

---

### So, what do you include on your logs?

---

### What should I log in my application? (color)

---

### Application Session start/stop
1. When the application start/stop
2. Include additional messages at the start and end of these sections.

---

### User Session start/stop
1.Log distinctive messages at the start and end of each of these logical sessions.

---

### Unhandled Exceptions
1. Passing the exception object as well as what context you have.

---

### Handled Exceptions
1. Where an exception is consumed within a catch block that you log the exception with an Informational severity

---

### Process Entrance and Exit
1. Incoming requests
2. Database query
3. Web service

---

### Significant User Actions
1. Button actions
2. Navigating to a new context
3. Any message box / modal prompt displayed.
4. Expensive operations

---

### Display Help requests
1. Erro de atribuição fundamental
2. Efeito do falso consenso

---

### Cancelled Actions

---

### What Not to Log (color)

---

### Avoid logging simple routine actions

---

### Avoid logging in tight loops

---

### Think carefully about sensitive information

---

### Best practices (color)

---

### Message Priorities/Levels
- fatal
- error
- warn 
- info 
- debug
- trace

---

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

---

### Don’t log large messages!
Logging costs money.

---

### Don’t Write Logs by Yourself

---

### Add Context to Your Log Messages

    // instead of this
    Transaction failed

    // make this
    Transaction 2346432 failed: cc number checksum incorrect

---

### Conclusion
In conclusion logs offering invaluable insights into its behavior, health, and performance.

---

### I ❤️ Logs

Luís Antônio (https://tonhao.dev)
