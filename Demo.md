# 🚀 Application Security Bootcamp - Demo Class (Day 1)
>
> **Objective:** Introduce the student to Cybersecurity and Application Security in a simple and engaging way.

---

# 👨‍🏫 Introduction

Hi! Welcome to the Application Security Bootcamp.

Before we start learning hacking, secure coding, or security tools, we first need to understand **how applications work** and **why they get hacked**.

By the end of today's session, you will understand:

- What Cybersecurity is
- What Application Security is
- Why companies hire Application Security Engineers
- How hackers attack applications
- The roadmap of this course

---

# 🎯 Learning Outcomes

After today's class, you will be able to:

- Explain Cybersecurity in simple words.
- Explain Application Security.
- Understand the CIA Triad.
- Understand how a web application works.
- Identify basic security risks.
- Know what you will learn in the upcoming classes.

---

# ❓ Ice Breaker

Let's start with a few simple questions.

### Question 1

Which applications do you use every day?

Examples:

- WhatsApp
- Instagram
- YouTube
- Amazon
- PhonePe
- ChatGPT

---

### Question 2

Imagine your Instagram account gets hacked.

How would you feel?

Possible answers:

- Personal photos leaked
- Messages leaked
- Account deleted
- Someone impersonates you

Now imagine...

Instead of your Instagram account...

The **entire Instagram application** gets hacked.

Millions of users could lose their data.

This is why Application Security exists.

---

# 🔒 What is Cybersecurity?

Cybersecurity is the practice of protecting:

- Computers
- Networks
- Applications
- Servers
- Data

from hackers and cyber attacks.

### Simple Example

Think about your home.

Your home has:

- Doors
- Locks
- CCTV
- Security Guard

Why?

To stop thieves.

Applications also need protection.

Instead of thieves...

They have hackers.

---

# 💻 What is Application Security?

Application Security means protecting software applications from security vulnerabilities and cyber attacks.

Examples of applications:

- Instagram
- WhatsApp
- Amazon
- Flipkart
- Swiggy
- Banking Apps

Every application stores valuable data.

That is why attackers target them.

---

# 🤔 Activity

Think about your favorite application.

Answer these questions.

1. What data does it store?
2. What happens if hackers steal that data?
3. Would users trust the application again?

---

# 🌍 How Does a Web Application Work?

```
User

↓

Browser

↓

Internet

↓

Application Server

↓

Database
```

### Example

You open Instagram.

↓

You enter your username and password.

↓

The browser sends a request.

↓

Instagram checks the credentials.

↓

Database verifies your account.

↓

Instagram sends the response.

Everything happens in just a few milliseconds.

---

# 🎯 What Can Hackers Attack?

Hackers may target:

- Login pages
- Password reset pages
- Search functionality
- Payment pages
- APIs
- File uploads

Their goal is to steal:

- Passwords
- Credit card information
- Personal data
- Business secrets

---

# 🏦 Real-Life Example

Imagine a banking website.

A customer logs in and views their account.

The URL looks like this:

```
https://bank.com/account?id=1001
```

Now imagine someone changes it to:

```
https://bank.com/account?id=1002
```

If they can see another customer's account...

That is a security vulnerability.

This is called **IDOR (Insecure Direct Object Reference)**.

Don't worry about the name today.

We'll learn it in detail later.

---

# 🛡 CIA Triad

Cybersecurity is built on three important principles.

## 1. Confidentiality

Only authorized people should access information.

Example:

Only you should read your WhatsApp messages.

---

## 2. Integrity

Data should not be modified without permission.

Example:

Your bank balance should not change unexpectedly.

---

## 3. Availability

Systems should always be available.

Example:

UPI should work whenever you need to make a payment.

---

# 👨‍💻 Who is an Application Security Engineer?

An Application Security Engineer helps developers build secure applications.

Responsibilities include:

- Finding vulnerabilities
- Reviewing source code
- Performing security testing
- Working with developers
- Preventing cyber attacks

---

# 👨‍💻 Ethical Hacker vs Hacker

| Hacker | Ethical Hacker |
|---------|----------------|
| Hacks illegally | Hacks with permission |
| Steals data | Protects data |
| Works for criminals | Works for organizations |

---

# 🚨 How Applications Get Hacked

```
Developer writes code

↓

Mistake in the code

↓

Application deployed

↓

Hacker finds the mistake

↓

Application hacked

↓

Data stolen
```

Our goal is to identify those mistakes before hackers do.

---

# 🌐 Modern Applications

Applications today are more than just websites.

Examples include:

- Web Applications
- Mobile Applications
- REST APIs
- Microservices
- Cloud Applications

You will learn how to secure all of them.

---

# 🧪 Demo

Visit:

https://juice-shop.herokuapp.com

Observe:

- Login page
- Product page
- Search functionality
- Shopping cart

Question:

Can you identify which pages may contain security risks?

Don't try to hack anything today.

Just observe.

---

# 🔍 Browser Developer Tools

Press:

```
F12
```

Open the **Network** tab.

Refresh the page.

Observe:

- Requests
- Responses
- Headers
- Status Codes

Explain:

Whenever you click a button, your browser sends an HTTP request to the server.

We'll inspect and modify these requests in future classes using **Burp Suite**.

---

# 🛣 Course Roadmap

```
Cybersecurity

↓

Networking

↓

Linux

↓

HTTP

↓

Web Applications

↓

OWASP Top 10

↓

Burp Suite

↓

API Security

↓

Secure Coding

↓

DevSecOps

↓

Capstone Project

↓

Internship

↓

Job
```

---

# 🎯 Career Opportunities

After completing this course, you can pursue roles such as:

- Application Security Engineer
- Security Engineer
- DevSecOps Engineer
- Penetration Tester
- Secure Code Reviewer
- API Security Engineer

---

# 📝 Homework

## Task 1

List 10 applications you use every day.

For each application, answer:

- What data does it store?
- Why is that data valuable?
- What could happen if it gets hacked?

---

## Task 2

Create accounts on:

- PortSwigger Web Security Academy
- TryHackMe

(No need to solve labs yet.)

---

## Task 3

Install the following software:

- Google Chrome
- Firefox
- Visual Studio Code

---

# 💡 Key Takeaway

Cybersecurity is not just about hacking.

It is about protecting applications and users from real-world threats.

Every secure application starts with understanding how it works, identifying potential weaknesses, and fixing them before attackers can exploit them.

This course will help you build that mindset step by step.

---

# 🎉 Next Class Preview

In the next session, we will learn:

- How the Internet works
- What happens when you type a website URL
- DNS
- IP Addresses
- Ports
- HTTP vs HTTPS
- Client and Server Communication

By the end of the next class, you'll understand exactly how your browser communicates with a web server.
