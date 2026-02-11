Regular Expression (RegEx) is a powerful tool used to search, match, validate, extract or modify text based on specific patterns. In Python, the built-in re module provides support for using RegEx. It allows you to define patterns using special characters like \d for digits, ^ for the beginning of a string and many more.

<img width="1234" height="346" alt="image" src="https://github.com/user-attachments/assets/17df75d8-970f-4d97-9dfb-2ec61bc9ac22" />

MetaCharacters In RegEx
To understand the RE analogy, MetaCharacters are useful, important and will be used in functions of module re. Below is the list of metacharacters.

<img width="1154" height="711" alt="image" src="https://github.com/user-attachments/assets/fd570ec6-bde0-44fb-8fe7-cdeec0c270d6" />

Special Sequences
Special sequences in Python RegEx begin with a backslash (\) and are used to match specific character types or positions in a string. They simplify complex patterns and enhance readability.

<img width="846" height="690" alt="image" src="https://github.com/user-attachments/assets/ead50e6a-9ad3-4e5f-8bca-fc6d94720ee6" />
<img width="826" height="569" alt="image" src="https://github.com/user-attachments/assets/e27249fb-fce6-4f6f-9715-231513b34c4f" />

Basic RegEx Patterns
Let's understand some of the basic regular expressions. They are as follows:

1. Character Classes
Character classes allow matching any one character from a specified set. They are enclosed in square brackets [].

import re
print(re.findall(r'[Gg]eeks', 'GeeksforGeeks: \
                 A computer science portal for geeks'))

<img width="744" height="121" alt="image" src="https://github.com/user-attachments/assets/bca659f9-7a43-417e-afb6-2654b7ce06ca" />

2. Ranges
In RegEx, a range allows matching characters or digits within a span using - inside []. For example, [0-9] matches digits, [A-Z] matches uppercase letters.
<img width="797" height="117" alt="image" src="https://github.com/user-attachments/assets/1b4279f3-d12e-4fa7-9ece-b9c1a788186a" />

3. Negation
Negation in a character class is specified by placing a ^ at the beginning of the brackets, meaning match anything except those characters.

<img width="848" height="509" alt="image" src="https://github.com/user-attachments/assets/2e6cac02-3591-43f8-8855-de7e7ace753c" />
<img width="870" height="581" alt="image" src="https://github.com/user-attachments/assets/7f5d9637-9156-43f8-afe3-412768da4a61" />


4. Beginning and End of String
The ^ character chooses the beginning of a string and the $ character chooses the end of a string.




import re


# Beginning of String
match = re.search(r'^Geek', 'Campus Geek of the month')
print('Beg. of String:', match)

match = re.search(r'^Geek', 'Geek of the month')
print('Beg. of String:', match)

# End of String
match = re.search(r'Geeks\$', 'Compute science portal-GeeksforGeeks')
print('End of String:', match)
import re
​
​
# Beginning of String
match = re.search(r'^Geek', 'Campus Geek of the month')
print('Beg. of String:', match)
​
match = re.search(r'^Geek', 'Geek of the month')
print('Beg. of String:', match)
​
# End of String
match = re.search(r'Geeks\$', 'Compute science portal-GeeksforGeeks')
print('End of String:', match)
<img width="912" height="387" alt="image" src="https://github.com/user-attachments/assets/9e11ce1d-699e-4d09-90aa-9a9c1426fac4" />

<img width="874" height="516" alt="image" src="https://github.com/user-attachments/assets/e25ba4e0-d5b3-45e3-bc19-f9c6a9619f60" />
<img width="876" height="616" alt="image" src="https://github.com/user-attachments/assets/3ca94028-21dc-4bb7-b39f-ddfcfb2787b1" />
7.1 Repetition ranges
The repetition range is useful when you have to accept one or more formats. Consider a scenario where both three digits, as well as four digits, are accepted. Let's have a look at the regular expression.




import re
​
​
print('Three Digit:', re.search(r'[\d]{3,4}', '189'))
print('Four Digit:', re.search(r'[\d]{3,4}', '2145'))

Output
Three Digit: <_sre.SRE_Match object; span=(0, 3), match='189'>
Four Digit: <_sre.SRE_Match object; span=(0, 4), match='2145'>
7.2 Open-Ended Ranges
There are scenarios where there is no limit for a character repetition. In such scenarios, you can set the upper limit as infinitive. A common example is matching street addresses. Let's have a look  


import re


print(re.search(r'[\d]{1,}','5th Floor, A-118,\
Sector-136, Noida, Uttar Pradesh - 201305'))
Output
<_sre.SRE_Match object; span=(0, 1), match='5'>


<img width="883" height="446" alt="image" src="https://github.com/user-attachments/assets/76085d25-5046-4c7a-a237-dc966e18e652" />

<img width="864" height="472" alt="image" src="https://github.com/user-attachments/assets/5b82f789-0022-4a27-bcf0-a3b25523359a" />

<img width="863" height="438" alt="image" src="https://github.com/user-attachments/assets/e52c74f6-e61d-4dc1-b3c7-edeb4ae0d9e5" />

<img width="849" height="441" alt="image" src="https://github.com/user-attachments/assets/40d248fe-ed58-4884-ac08-bdfa787d9638" />
<img width="886" height="435" alt="image" src="https://github.com/user-attachments/assets/1aa544c5-e888-4ca4-824a-f38ac65ba554" />

<img width="886" height="475" alt="image" src="https://github.com/user-attachments/assets/8af2040c-7953-4b30-8f38-82c926f9b8c5" />

<img width="872" height="547" alt="image" src="https://github.com/user-attachments/assets/1e076da6-3e0b-4210-ba80-885367786e70" />

<img width="856" height="602" alt="image" src="https://github.com/user-attachments/assets/350cb998-0b88-4779-bed6-6b04692b377a" />

<img width="828" height="316" alt="image" src="https://github.com/user-attachments/assets/15ec57e9-c251-4c57-ac0a-a979a439cf25" />
<img width="845" height="619" alt="image" src="https://github.com/user-attachments/assets/217ca4be-72ca-4eca-b5de-a5fa0e771360" />
<img width="850" height="631" alt="image" src="https://github.com/user-attachments/assets/34944180-e792-467e-85de-1b8d35ecb155" />

Explanation:

re.compile(...) creates a reusable regular expression pattern to match dates in the DD-MM-YYYY format.
regex.search() finds the date match and regex.sub(r'\1.\2.\3', ...) replaces '26-08-2020' with '26.08.2020'.
