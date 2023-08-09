# TASK - 1
# Random_password_generator

import random
import string

def generate_password(length=25):
    characters = string.ascii_letters + string.digits + string.punctuation
    password = ''.join(random.choice(characters) for _ in range(length))
    return password

def calculate_password_strength(password):
    lowercase_letters = set(string.ascii_lowercase)
    uppercase_letters = set(string.ascii_uppercase)
    digits = set(string.digits)
    symbols = set(string.punctuation)

    strength = 0.0
    if any(char in lowercase_letters for char in password):
        strength += 0.25
    if any(char in uppercase_letters for char in password):
        strength += 0.25
    if any(char in digits for char in password):
        strength += 0.25
    if any(char in symbols for char in password):
        strength += 0.25

    return strength

password = generate_password()
strength = calculate_password_strength(password)

print("Generated Password:", password)
print("Password Strength:", round(strength, 2))
