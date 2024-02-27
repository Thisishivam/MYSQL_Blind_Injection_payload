# MYSQL_Blind_Injection_payload
    1.0'XOR(if(now()=>sysdata(),sleep(5),0))XOR'Z
   
Explanation: 
This MySQL time-based payload is designed to delay the query execution by 5 seconds using the sysdata(),sleep(5) function. It employs XOR operations to manipulate the condition check, attempting to bypass           security measures and extract information through timing analysis.' Z': This part of the payload is just a dummy string to make the query syntactically correct.

    2.if(now()=sysdate(), sleep(5),0) 

Explanation:
This MySQL time-based payload is a SQL injection attack that delays execution if the current time is equal to the current system date (i.e., now() equals sysdate()). It sleeps for 5 seconds if the condition is      true, otherwise, it does nothing (0). This payload is typically used to manipulate database behavior, potentially causing delays or disruptions in the application's response.

    3.'XOR(if(now()=sysdate(),sleep(5),0))XOR'
Explanation: 
This MySQL payload utilizes the XOR operation to execute a time-based attack. The payload checks if the current time (now()) is equal to the system date (sysdate()). If it is, it will execute a sleep function for 5 seconds, otherwise, it returns 0. This can be used to perform a time-based blind SQL injection attack, where the response time of the server is used to infer information about the database.

    4.'XOR(if (now()=sysdate(),sleep(5*1),0))OR'
Explanation: 
This MySQL time-based payload is designed to exploit a SQL injection vulnerability. It attempts to delay the response from the database by checking if the current time (now()) is equal to the system date (sysdate()). If they match, it will cause the database to sleep for 5 seconds (sleep(5*1)), otherwise, it returns 0. The XOR logic is used to obfuscate the payload.

    5.if(now()=sysdate(),sleep(5),0)/"XOR(if(now()=sysdate(), sleep(5),0))OR"/
Explanation: The payload consists of two parts separated by the XOR operator:

if(now()=sysdate(),sleep(5),0): This part checks if the current date and time (now()) is equal to the system date and time (sysdate()). If they match, it executes the sleep(5) function, causing the database to pause for 5 seconds. Otherwise, it returns 0.

if(now()=sysdate(), sleep(5),0): This part is similar to the first, but it is enclosed within an XOR operation, which means it will return true if either one of its operands is true. In this case, it will execute the sleep(5) function if the current date and time matches the system date and time.

The OR operator (OR) at the end indicates that either condition being true is sufficient for the payload to execute.

    6.if(now()=sysdate(),sleep(5),0)/*'XOR(if(now()=sysdate(), sleep(5),0))OR' "XOR(if (now()=sysdate(),sleep(5),0))OR"*/
Explanation: 
This MySQL payload is attempting to exploit a potential vulnerability in a SQL injection attack, specifically targeting a time-based blind SQL injection. Let's break down the payload:

if(now()=sysdate(),sleep(5),0): This part of the payload checks if the current date and time (now()) is equal to the system date (sysdate()). If it is, the server will sleep for 5 seconds (sleep(5)), indicating a successful injection. Otherwise, it will return 0.

XOR: This is the logical XOR operator, which returns true if exactly one of the expressions it connects is true.

OR: This is the logical OR operator, which returns true if at least one of the expressions it connects is true.

'XOR(if(now()=sysdate(), sleep(5),0))OR': This part of the payload is enclosed in single quotes, which could potentially help bypass certain input filters. It essentially repeats the previous logic with some added text.

'*/': This part of the payload is commented out and will not be executed. It's an attempt to bypass input validation or detection mechanisms.

Overall, this payload is trying to inject malicious code into a SQL query to determine if the injection is successful by causing a delay in the server's response time. It uses various logical operators and comments to obfuscate the malicious intent and potentially bypass security measures.

    7.if(now()=sysdate(), sleep(5),0)/'XOR(if (now()=sysdate(), sleep(5),0))OR' "XOR(if (now()=sysdate(),sleep(5),0) and 5=5)"/
Explanation: if(now()=sysdate(), sleep(5),0): This part of the payload checks if the current time (now()) is equal to the system date (sysdate()). If they are equal, it sleeps for 5 seconds (sleep(5)), otherwise, it returns 0.

/: This is a division operator.

'XOR(if (now()=sysdate(), sleep(5),0))OR': This is an attempt to use the logical XOR operator to inject a condition that will always evaluate to true. It checks if the result of the first condition (if the current time is equal to the system date) is XORed with the result of the sleep function, and then ORed with 1. This is meant to bypass certain security mechanisms by always evaluating to true.

'XOR(if (now()=sysdate(),sleep(5),0) and 5=5)': This part is similar to the previous one but adds an additional condition (5=5) which is always true. The intention is to ensure that the injected condition will always be true, regardless of the outcome of the initial time-based condition.

Overall, this payload is attempting to exploit a vulnerability in the SQL query to cause a delay in the response time if the condition is true, indicating that the injection was successful.

    8.SLEEP(5)/*' or SLEEP(5) or'*or SLEEP(5) or "*/

Explanation: The MYSQL time-based payload SLEEP(5)/*' or SLEEP(5) or'*or SLEEP(5) or "*/ is a SQL injection technique used to exploit vulnerabilities in web applications that interact with a MySQL database.

The breakdown of the payload:

SLEEP(5): This is a MySQL function that pauses the execution of a query for a specified number of seconds. In this case, it pauses for 5 seconds.

/*' or SLEEP(5) or'*or SLEEP(5) or "*/: This part of the payload is designed to comment out the rest of the SQL query and inject the SLEEP(5) function. The /* starts a multi-line comment in SQL, effectively ignoring anything that comes after it until the */ is encountered. The payload includes various combinations of single quotes, double quotes, and the or operator to try to bypass any input validation or filtering mechanisms that the application may have in place.

    9.(SELECT * FROM (SELECT(SLEEP(5)))YYYY)--

Explanation: The breakdown of the payload:

(SELECT * FROM (SELECT(SLEEP(5))): This part of the payload creates a subquery where the SLEEP(5) function is called. The SLEEP() function in MySQL causes the database server to pause for the specified number of seconds (in this case, 5 seconds).

YYYY): This part appears to be an attempt to close off parentheses, although it seems like there might be a typo or misplaced characters here. It could be a placeholder or part of a larger SQL injection payload.

--: This part represents a comment in SQL. Everything after -- on the same line is treated as a comment and ignored by the database server. This is often used to prevent errors in injection payloads and to comment out the rest of the original query.

    10.(select(0) from(select(sleep(5)))v)%2f⋆'+

Explanation: The breakdowm of the payload

(select(0) from(select(sleep(5)))v): This part of the payload is a subquery that causes the database to sleep for 5 seconds. The sleep() function is a MySQL function that pauses the execution of a query for a specified number of seconds.

%2f⋆'+: These characters are URL encoded. %2f represents the forward slash (/), and %2a represents the asterisk (*). Together, they form the comment delimiter /*. The + sign is a URL-encoded space. This part of the payload is likely attempting to comment out any remaining parts of the original SQL query to avoid syntax errors.

The payload is attempting to exploit a time-based blind SQL injection vulnerability. By causing the database to sleep for a specified amount of time, an attacker can infer whether their injected SQL code had any effect based on the response time of the application. If the response is delayed by the specified sleep time, it indicates that the injection was successful, allowing the attacker to proceed with further exploitation.
