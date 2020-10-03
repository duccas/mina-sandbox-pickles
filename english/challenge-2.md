---
description: 'Create and Send Fun tokens (up to 1,500 pts)'
---

# Challenge \#2

### **New Feature: Fun tokens on Mina.**

Users can now create their own \(layer 2\) tokens on Mina Protocol, for example for a future Snapp \(SNARK-powered application\) that will be built on top of Mina.

{% hint style="info" %}
1. Reward for the mint 500 pts.
2. Additional reward of 1,000 pts for sending tokens to the following address: **B62qoDWfBZUxKpaoQCoFqr12wkaY84FrhxXNXzgBkMUi2Tz4K8kBDiv**
{% endhint %}

### 1. Let's create tokens

To access any [Mina CLI](https://minaprotocol.com/docs/cli-reference) commands:

```text
sudo docker exec -it mina bash
```

First you need to unlock your account:

```text
mina accounts unlock -public-key B62qrPN5Y5yq8kGE3FbVKbGTdTAJNdtNtB5sNVpxyRwWGcDEhpMzc8g
```

In the password entry field, do not write anything and press ENTER.

Now let's create tokens:

```text
mina client create-token -sender B62qrPN5Y5yq8kGE3FbVKbGTdTAJNdtNtB5sNVpxyRwWGcDEhpMzc8g
```

In response, we get the following:

{% code title="\#EXAMPLE OF ANSWER" %}
```text
Dispatched create new token command with ID 2cUDm3QoJ14znWj5LxN8hjwwuvtwi9FGXcy56i4dPvYizPNwr3V9c9ePYxy3pJKjgogNx28jwHhqupi6wHFgXBmU5iX27iK1zUvJarj6wJsUG8segWXc4LGPed66YbYk3u9HiWw4v8cYYEqcy1mU6hqfj5JPMPthEBifxUMHZTqCwZmYWSdiERxB6PtPEdXVraWaYPVU4Q8vtpSN7oSTK1AXyXLYYR835CBrNSmgbLvoBDNroCKwcQrzw4b76BFNLe6EuWvBcMgX6npeeAbPg8z8iJ4PKz3gA64o1Y72kCrqyqus718LwXcmp5jxsYvJB2CJHzyZ
```
{% endcode %}

### 2. Get the ID of the tokens

To carry out the following operations, we need to know the ID of the tokens. We get it with the following command:

```text
mina client get-tokens -public-key B62qrPN5Y5yq8kGE3FbVKbGTdTAJNdtNtB5sNVpxyRwWGcDEhpMzc8g
```

In response, we get the following:

{% code title="\#EXAMPLE OF ANSWER" %}
```text
Accounts are held for token IDs:
1
```
{% endcode %}

### 3. Check the token**s balance**

The token balance is checked by the command below with your token ID:

```text
mina client get-balance -token 1 -public-key B62qrPN5Y5yq8kGE3FbVKbGTdTAJNdtNtB5sNVpxyRwWGcDEhpMzc8g
```

We will see the balance of mina tokens.

### 4. Mint tokens

To mint new tokens, you need to run the command `mint-tokens`. 1,000 tokens will be created in the account of the sender of the transaction under token ID 2.

```text
mina client mint-tokens -sender B62qrPN5Y5yq8kGE3FbVKbGTdTAJNdtNtB5sNVpxyRwWGcDEhpMzc8g -token 2 -amount 1000
```

Let's check the balance with the command \(the balance will not appear immediately, you need to wait about 5 minutes\):

```text
mina client get-balance -token 2 -public-key B62qrPN5Y5yq8kGE3FbVKbGTdTAJNdtNtB5sNVpxyRwWGcDEhpMzc8g
```

After a while, we should see 1,000 mina tokens on our balance.

{% code title="\#EXAMPLE OF ANSWER" %}
```text
mina client get-balance -token 2 -public-key B62qrPN5Y5yq8kGE3FbVKbGTdTAJNdtNtB5sNVpxyRwWGcDEhpMzc8g
Balance: 1000 tokens
```
{% endcode %}

### 5. Sending tokens

On the instructions we need to send 50 tokens to the address`B62qoDWfBZUxKpaoQCoFqr12wkaY84FrhxXNXzgBkMUi2Tz4K8kBDiv`.  
To do this, we first need to add a recipient with the command below:

```text
mina client create-token-account -sender B62qrPN5Y5yq8kGE3FbVKbGTdTAJNdtNtB5sNVpxyRwWGcDEhpMzc8g -receiver B62qoDWfBZUxKpaoQCoFqr12wkaY84FrhxXNXzgBkMUi2Tz4K8kBDiv -token 2
```

Now let's send 50 tokens.  
In the field `-memo "My First TX",` instead of `My First TX`, you can enter anything you want. Or leave it as it is.

```text
mina client send-payment -sender B62qrPN5Y5yq8kGE3FbVKbGTdTAJNdtNtB5sNVpxyRwWGcDEhpMzc8g -receiver B62qoDWfBZUxKpaoQCoFqr12wkaY84FrhxXNXzgBkMUi2Tz4K8kBDiv -token 2 -memo "My First TX" -amount 50
```

After a while, the tokens will be sent to the address. To check your balance, enter the following command:

```text
mina client get-balance -token 2 -public-key B62qoDWfBZUxKpaoQCoFqr12wkaY84FrhxXNXzgBkMUi2Tz4K8kBDiv
```

Now take a screenshot of the balance command output as shown below. 

![](../.gitbook/assets/image%20%283%29.png)

### 6. Filling out the form

To fill out the form for tasks Challenge \#1 and Challenge \#2 follow [this link](https://share.hsforms.com/1V-gRVnWZSLehZVB_F3sacQ4xuul).

1. You need to enter your email. 
2. Discord ID 
3. Block production time, which we counted in Challenge \#1 
4. Upload a screenshot of the block production logs and a text file with logs from Challenge \#1 
5. Upload a screenshot of the token balance at`B62qoDWfBZUxKpaoQCoFqr12wkaY84FrhxXNXzgBkMUi2Tz4K8kBDiv` from Challenge \#2

![](../.gitbook/assets/image%20%284%29.png)

