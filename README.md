# DS-python-aloui
import re

def is_valid_email(email):
    regex_email = r'^[a-zA-Z0-9_.+-]+@[a-zA-Z0-9-]+\.[a-zA-Z0-9-.]+$'
    return re.match(regex_email, email) is not None

def is_valid_password(password):
    regex_password = r'^(?=.*[a-z])(?=.*[A-Z])(?=.*\d)(?=.*[@$!%*?&])[A-Za-z\d@$!%*?&]{8}$'
    return re.match(regex_password, password) is not None

def save_to_file(email, password):
    with open('Enregistrement.txt', 'a') as file:
        file.write(f"Login: {email} - Password: {password}\n")

email = input("Entrez votre adresse e-mail : ")
password = input("Entrez votre mot de passe : ")

if is_valid_email(email) and is_valid_password(password):
    save_to_file(email, password)
    print("Enregistrement effectué avec succès dans Enregistrement.txt")
else:
    print("L'adresse e-mail ou le mot de passe ne respectent pas les critères spécifiés.")
    def authenticate(email, password):
    # Check if the provided credentials exist in the registration file
    with open('Enregistrement.txt', 'r') as file:
        for line in file:
            if f"Login: {email} - Password: {password}" in line:
                return True
        return False

def roulette_game():
    print("Exercice Mini Projet de la série 1 sur votre plateforme - Jouer à la Roulette")
    # Implement your roulette game logic here

def cesar_cipher():
    print("Décalage par CESAR")
    # Implement your Caesar Cipher logic here

def main_menu():
    print("\nMenu Principal:")
    print("A- Jouer à la Roulette")
    print("B- Décalage par CESAR")
    print("Q- Quitter le programme")

def roulette_menu():
    print("\nMenu Roulette:")
    print("a- Commencer à jouer")
    print("b- Revenir au menu principal")

def cesar_menu():
    print("\nMenu Décalage par CESAR:")
    print("a- Donnez un mot à chiffrer")
    print("b- Revenir au menu principal")

def authenticate_user():
    while True:
        email = input("Email: ")
        password = input("Password: ")
        if authenticate(email, password):
            return True
        else:
            print("Credentials incorrect. Please register.")
            return False

def main():
    while True:
        if not authenticate_user():
            register_user()

        main_menu()
        choice = input("Entrez votre choix : ")

        if choice.upper() == 'A':
            roulette_menu()
            # Implement logic for Roulette game
            # Based on user's choice perform relevant actions

        elif choice.upper() == 'B':
            cesar_menu()
            # Implement logic for CESAR cipher
            # Based on user's choice perform relevant actions

        elif choice.upper() == 'Q':
            print("Programme terminé.")
            break

        else:
            print("Choix invalide. Veuillez réessayer.")

if __name__ == "__main__":
    main()


    
