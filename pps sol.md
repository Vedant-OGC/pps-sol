---


---

<h3 id="from-attachments-1--2"><strong>From Attachments 1 &amp; 2</strong></h3>
<p><strong>Question 5: File Report (Lines, Words, Characters, Vowels, Consonants)</strong> A program that inputs a filename and generates a complete report of the file’s contents.</p>
<pre><code>def generate_file_report(filename):
    try:
        with open(filename, 'r') as file:
            text = file.read()

            # Calculations
            lines = text.count('\n') + 1 if text else 0
            words = len(text.split())
            characters = len(text)
            vowels = sum(1 for char in text.lower() if char in 'aeiou')
            consonants = sum(1 for char in text.lower() if char.isalpha() and char not in 'aeiou')

            # Output
            print(f'"lines": {lines}, "words": {words}, "characters": {characters}, "vowels": {vowels}, "consonants": {consonants}')

    except FileNotFoundError:
        print("FileNotFoundError")

# Example usage:
# generate_file_report('sample.txt')

</code></pre>
<p><strong>Question 6: Validating Filenames</strong> Check if a given filename is strictly one of the valid options (<code>data.txt</code>, <code>marks.txt</code>, <code>log.txt</code>).</p>
<pre><code>def check_valid_filename(filename):
    valid_files = ['data.txt', 'marks.txt', 'log.txt']

    if filename in valid_files:
        print("File opened successfully")
    else:
        print("FileNotFoundError")

# Example usage:
# check_valid_filename('data.txt')  # Output: File opened successfully
# check_valid_filename('result.txt') # Output: FileNotFoundError

</code></pre>
<hr>
<h3 id="from-attachments-3--4-set-ii"><strong>From Attachments 3 &amp; 4 (Set-II)</strong></h3>
<p><strong>Question 1: Unique Words from Social Media Comments</strong> Extract all unique words from a list of strings.</p>
<pre><code>def extract_unique_words(comments):
    all_words = []
    for comment in comments:
        all_words.extend(comment.split())

    unique_words = set(all_words)
    print(f"Unique Words: {unique_words}")
    return unique_words

comments = ["python is great", "python is easy", "coding is fun", "python coding"]
extract_unique_words(comments)

</code></pre>
<p><strong>Question 2: Merge Employee Dictionaries</strong> Merge two dictionaries. If an employee exists in both branches, keep the higher salary.</p>
<pre><code>def merge_employee_data(branch_a, branch_b):
    merged_data = branch_a.copy()

    for name, salary in branch_b.items():
        if name in merged_data:
            merged_data[name] = max(merged_data[name], salary)
        else:
            merged_data[name] = salary

    print(merged_data)
    return merged_data

branch_a = {"Alice": 50000, "Bob": 45000, "Charlie": 55000}
branch_b = {"Bob": 48000, "David": 40000, "Alice": 52000}
merge_employee_data(branch_a, branch_b)

</code></pre>
<p><strong>Question 3: Calculate Permutations P(n, r)</strong> Calculate permutations using a custom factorial function.</p>
<pre><code>def fact(num):
    if num == 0 or num == 1:
        return 1
    return num * fact(num - 1)

def permutations(n, r):
    return fact(n) // fact(n - r)

print(permutations(5, 2)) # Output: 20
print(permutations(4, 4)) # Output: 24

</code></pre>
<p><strong>Question 4: Recursive Power of Two Checker</strong> A recursive function to validate if a number is a power of 2.</p>
<pre><code>def is_power_of_two(n):
    if n &lt;= 0:
        return False
    if n == 1:
        return True
    if n % 2 != 0:
        return False
    return is_power_of_two(n // 2)

print(is_power_of_two(1)) # Output: True
print(is_power_of_two(5)) # Output: False

</code></pre>
<hr>
<h3 id="from-attachment-5-set-iii"><strong>From Attachment 5 (Set-III)</strong></h3>
<p><strong>Question 1: Library Reading Clubs Sets</strong> Find students in both clubs and students only in the Fiction Club.</p>
<pre><code>fiction_club = {'Rama', 'Sita', 'Lakshman', 'Anu'}
science_club = {'Sita', 'Anu', 'Ravi', 'Kiran'}

both_clubs = fiction_club.intersection(science_club)
only_fiction = fiction_club.difference(science_club)

print(f"Students in both clubs: {both_clubs}")
print(f"Students only in Fiction Club: {only_fiction}")

</code></pre>
<p><strong>Question 2: Analyze Exam Scores</strong> Analyze a list of students to find the highest, lowest, average, and top student.</p>
<pre><code>def analyze_scores(scores_dict):
    highest = max(scores_dict.values())
    lowest = min(scores_dict.values())
    average = sum(scores_dict.values()) / len(scores_dict)
    top_student = max(scores_dict, key=scores_dict.get)

    return {
        "highest": highest,
        "lowest": lowest,
        "average": average,
        "top_student": top_student
    }

scores = {"Alice": 85, "Bob": 72, "Charlie": 90, "Diana": 68}
print(analyze_scores(scores))

</code></pre>
<p><strong>Question 3: Extract Vowel Names</strong> Extract names starting with a vowel from a given list.</p>
<pre><code>def extract_vowel_names(names):
    vowels = ('A', 'E', 'I', 'O', 'U', 'a', 'e', 'i', 'o', 'u')
    return [name for name in names if name.startswith(vowels)]

names_list = ["Alice", "Bob", "Emma", "Charlie", "Olivia", "Uma", "John"]
print(extract_vowel_names(names_list))

</code></pre>
<p><strong>Question 4: Recursive Linear Search</strong> Implement linear search recursively to find a target’s index.</p>
<pre><code>def linear_search(arr, target, index=0):
    if index &gt;= len(arr):
        return -1
    if arr[index] == target:
        return index
    return linear_search(arr, target, index + 1)

arr =
print(linear_search(arr, 8)) # Output: 2

</code></pre>
<hr>
<h3 id="from-attachment-6-set-i"><strong>From Attachment 6 (Set-I)</strong></h3>
<p><strong>Question 1: Pairs Equal to Target Sum</strong> Find pairs of elements in a set whose sum equals a given target value.</p>
<pre><code>def find_pairs_with_sum(arr, target):
    pairs = []
    seen = set()
    for num in arr:
        complement = target - num
        if complement in seen:
            pairs.append([complement, num])
        seen.add(num)
    return pairs

arr =
target = 5
print(find_pairs_with_sum(arr, target)) # Output: [,]

</code></pre>
<p><strong>Question 2: Top 3 and Bottom 3 Sellers</strong> Identify the top 3 best-selling and bottom 3 worst-selling products from a promotional campaign.</p>
<pre><code>def analyze_sales(products):
    # Sort items based on units sold (descending)
    sorted_items = sorted(products.items(), key=lambda item: item, reverse=True)

    print("Top 3 Best Sellers:")
    for item in sorted_items[:3]:
        print(f"{item}: {item} units")

    print("Bottom 3 Worst Sellers:")
    # Get last 3 and sort ascending
    for item in sorted(sorted_items[-3:], key=lambda item: item):
        print(f"{item}: {item} units")

sales_data = {
    "Monitor Stand": 567, "Wireless Mouse": 1247, "USB-C Cable": 2103,
    "Phone Charger": 1892, "Desk Mat": 378, "Laptop Sleeve": 932,
    "Webcam HD": 1456, "Mechanical Keyboard": 843
}
analyze_sales(sales_data)

</code></pre>
<p><strong>Question 3: Pangram Checker</strong> Implement a function to check if a sentence contains every letter of the alphabet.</p>
<pre><code>import string

def check_pangram(s):
    alphabet = set(string.ascii_lowercase)
    return alphabet.issubset(set(s.lower()))

input_string = "Pack my box with five dozen liquor jugs! 12345"
print(check_pangram(input_string)) # Output: True

</code></pre>
<hr>
<h3 id="from-attachment-7-set-iii"><strong>From Attachment 7 (Set-III)</strong></h3>
<p><strong>Question 1: Suspicious Repeated Transactions</strong> Find transactions that appear in both Branch A and Branch B, printed in ascending order.</p>
<pre><code>def find_suspicious_transactions(branch_a, branch_b):
    suspicious = set(branch_a).intersection(set(branch_b))
    sorted_suspicious = sorted(list(suspicious))
    print(" ".join(map(str, sorted_suspicious)))

branch_a_tx =
branch_b_tx =
find_suspicious_transactions(branch_a_tx, branch_b_tx) # Output: 1003 1004

</code></pre>
<p><strong>Question 2: Consonant and Vowel Distribution</strong> Analyze given text and print the count of vowels and consonants.</p>
<pre><code>def phonetic_distribution(text):
    vowels = sum(1 for char in text.lower() if char in 'aeiou')
    consonants = sum(1 for char in text.lower() if char.isalpha() and char not in 'aeiou')
    print(f"vowels={vowels}, consonants={consonants}")

phonetic_distribution("Python 3.8 is awesome!") # Output: vowels=6 consonants=9

</code></pre>
<p><strong>Question 3: Prime Range in Descending Order</strong> Generate large prime numbers for RSA encryption within a given range <code>[a, b]</code> and present them in descending order.</p>
<pre><code>def is_prime(n):
    if n &lt;= 1: return False
    for i in range(2, int(n**0.5) + 1):
        if n % i == 0: return False
    return True

def prime_range(a, b):
    primes = [str(i) for i in range(b, a - 1, -1) if is_prime(i)]
    print(", ".join(primes))

prime_range(10, 50)
# Output: 47, 43, 41, 37, 31, 29, 23, 19, 17, 13, 11

</code></pre>
<p><strong>Question 4: Recursive Sum of Natural Numbers</strong> Implement a recursive function to find the sum of the first <code>n</code> natural numbers.</p>
<pre><code>def recursive_sum(n):
    if n &lt;= 1:
        return n
    return n + recursive_sum(n - 1)

print(recursive_sum(5)) # Output: 15

</code></pre>
<p><strong>Question 5: Identify Longest Word in a Text File</strong> Read a file to identify and print the longest word along with its length.</p>
<pre><code>def find_longest_word(filename):
    try:
        with open(filename, 'r') as file:
            words = file.read().split()
            if not words: return

            longest_word = max(words, key=len)
            print(f"{longest_word} {len(longest_word)}")
    except FileNotFoundError:
        print("File not found")

# Example usage:
# find_longest_word('document.txt')

</code></pre>
<p><strong>Question 6: Handle Incompatible Types Error</strong> Write a program to handle the error when trying to add a string and a number together.</p>
<pre><code>def add_inputs(num_val, str_val):
    try:
        result = num_val + str_val
        print(result)
    except TypeError:
        print("TypeError: Cannot add a string and a number together. Incompatible types used.")

add_inputs(5, "Hello")

</code></pre>

