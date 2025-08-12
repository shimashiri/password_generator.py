# password_generator.py
import random
import string

def generate_password(length=10):
    if length < 5:
        raise ValueError("Password length should be at least 6 characters.")
    
    characters = string.ascii_letters + string.digits + string.punctuation
    password = ''.join(random.choice(characters) for _ in range(length))
    return password

if __name__ == "__main__":
    try:
        length = int(input("Enter desired password length: "))
        print("Generated password:", generate_password(length))
    except ValueError as e:
        print("Error:", e)
