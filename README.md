import re

def check_password_strength(password):
    strength = 0
    if len(password) >= 8:
        strength += 1
    if re.search(r"[A-Z]", password):
        strength += 1
    if re.search(r"[a-z]", password):
        strength += 1
    if re.search(r"[0-9]", password):
        strength += 1
    if re.search(r"[!@#$%^&*(),.?\":{}|<>]", password):
        strength += 1

    levels = ["Weak", "Moderate", "Strong", "Very Strong", "Excellent"]
    return levels[strength-1] if strength > 0 else "Very Weak"

password = input("Enter a password: ")
print("Password strength:", check_password_strength(password))
