# SQL-Injections
## What is SQL Injections?
### a. Definitions
 Structured Query Language (SQL) is a programming language for storing and processing information in relational databases. Relational databases store information as tables with rows and columns that represent data attributes and various relationships between data values.

 SQL Injection is a technique that takes advantage of query vulnerabilities in applications. Is done by inserting an additional piece of SQL to distort the original query, thereby allowing you to exploit data from the database. SQL injection can allow attackers to perform actions like a webmaster, on the application's database.

 ![image](https://github.com/sungnhan/SQL-Injections/assets/169170652/227363ee-d4e6-4d9e-adc5-68f274acab0d)

 ### b. Types of SQL Injection
 `SQL Injection` can be classified into three major categories  **_In-band SQLi_**, **_Inferential SQLi_** and **_Out-of-band SQLi_**.

 ![image](https://github.com/sungnhan/SQL-Injections/assets/169170652/fffb9a67-6256-4c03-9cf3-5f7bc192de3f)

 #### In-band SQLi (Classic SQLi)
   * In-band SQL Injection is the most common and easy-to-exploit of SQL Injection attacks. In-band SQL Injection occurs when an attacker is able to use the same communication channel to both launch the attack and gather results.
   * The two most common types of in-band SQL Injection are _Error-based SQLi_ and _Union-based SQLi_.

#### Inferential SQLi (Blind SQLi)
   * Inferential SQL Injection, unlike in-band SQLi, may take longer for an attacker to exploit, however, it is just as dangerous as any other form of SQL Injection. In an inferential SQLi attack, no data is actually transferred via the web application and the attacker would not be able to see the result of an attack in-band (which is why such attacks are commonly referred to as [blind SQL Injection attacks](https://www.acunetix.com/websitesecurity/blind-sql-injection/)). Instead, an attacker is able to reconstruct the database structure by sending payloads, observing the web application’s response and the resulting behavior of the database server.
   * The two types of inferential SQL Injection are _Blind-boolean-based SQLi_ and _Blind-time-based SQLi_.

#### Out-of-band SQLi
   * [Out-of-band SQL Injection](https://www.acunetix.com/blog/articles/blind-out-of-band-sql-injection-vulnerability-testing-added-acumonitor/) is not very common, mostly because it depends on features being enabled on the database server being used by the web application. Out-of-band SQL Injection occurs when an attacker is unable to use the same channel to launch the attack and gather results.
   * Out-of-band techniques, offer an attacker an alternative to inferential time-based techniques, especially if the server responses are not very stable (making an inferential time-based attack unreliable).

## Causes of SQL Injection
### a. Example
Testing for this vulnerability can be done very easily. Sometimes we just need to enter `'` or `"` symbol in the fields under test. If it returns any unexpected or unusual message, then we can be sure that SQL Injection is possible for that field.

*For example*: _A facebook sign up form_

![image](https://github.com/sungnhan/SQL-Injections/assets/169170652/c59f4f69-f980-4163-b0ad-d561d47c42d9)

    if(isset($_POST['username']) && isset($_POST['password'])){
    $sql = "SELECT * FROM tbl_user WHERE username='". $_POST['username'] . "' AND password = '" .$_POST['password'] ."'"; } 

If the user no longer enters normally and, for example, adds a quote ' or ", your line of code will immediately fail. Or they can change it into a query that is always correct as follows.

`SELECT * FROM tbl_user WHERE username = '' OR '1' = '1' and password = '' OR '1' = '1'`

### b. Common Causes of SQL Injection
* Old, Legacy, or Lazy Code
Sometimes code was secure enough or adequate when it was written, but as time passed and technology changed, what was secure 10 years ago is no longer acceptable.

* Outdated/Unpatched Applications
Making use of unsupported or legacy software or features introduces security holes that may not be patched or caught as quickly as they would with modern software.

Running patched and modern versions of software are critical to avoiding security exploits, including SQL injection. Continuously monitoring for new security vulnerabilities and reacting as needed is an important step towards avoiding unnecessary surprises.

* Security Assumptions
Often, we are led to a false sense of security due to the isolation of different application teams or environments. If we are led to believe that an application’s web forms are protected against injection by default, then we might be lax when developing stored procedures or other database objects.

* Failure to Layer Security
### c. Exploits
What can attackers do? Here are some examples:
* Download unauthorized data
* Delete/modify data
* Permanently destroy data/backups
* Long-term monitor a system
* Infect systems with viruses or malware
* Alter security to allow/disallow access as deemed fit by the hacker
* Encrypt/steal/alter data and hold it for ransom
* Publicly shame an organization via a web or social media hack
* Use data to infiltrate an organization or its business operations







