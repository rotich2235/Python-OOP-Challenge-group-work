# Python-OOP-Challenge-group-work
**pet.py**
# ==============================================
# OOP Digital Pet Challenge - Virtual Pet Game
# Group Members:
# - Elias
# - Hosanna
# - Ali Abdi
# - George
# - Kelvin
# - Rotich Elkana
# - Sarah
# - Lencer
# - Kennedy
# ==============================================

class Pet:
    def __init__(self, name):
        self.name = name
        self.hunger = 5
        self.energy = 5
        self.happiness = 5
        self.tricks = []

    def feed(self, food_type):
        if food_type.lower() == "meat":
            self.hunger = max(0, self.hunger - 4)
            self.happiness = min(10, self.happiness + 2)
            print(f"{self.name} devours the meat! 🍖")
        elif food_type.lower() == "green vegetables":
            self.hunger = max(0, self.hunger - 2)
            self.happiness = min(10, self.happiness + 1)
            print(f"{self.name} munches on the veggies! 🥦")
        else:
            print(f"{self.name} doesn't recognize that food. ❓")

    def sleep(self):
        self.energy = min(10, self.energy + 5)
        print(f"{self.name} is sleeping... 😴")

    def play(self):
        if self.energy >= 2:
            self.energy -= 2
            self.happiness = min(10, self.happiness + 2)
            self.hunger = min(10, self.hunger + 1)
            print(f"{self.name} is playing! 🎾")
        else:
            print(f"{self.name} is too tired to play. 💤")

    def train(self, trick):
        self.tricks.append(trick)
        self.happiness = min(10, self.happiness + 1)
        print(f"{self.name} learned a new trick: {trick}! 🐾")

    def show_tricks(self):
        if self.tricks:
            print(f"{self.name} knows these tricks: {', '.join(self.tricks)}")
        else:
            print(f"{self.name} doesn't know any tricks yet.")

    def get_status(self):
        print(f"\n📋 Status of {self.name}:")
        print(f"  Hunger: {self.hunger}/10")
        print(f"  Energy: {self.energy}/10")
        print(f"  Happiness: {self.happiness}/10\n")

**main.py**
# ==============================================
# OOP Digital Pet Challenge - Virtual Pet Game
# Group Members:
# - Elias
# - Hosanna
# - Ali Abdi
# - George
# - Kelvin
# - Rotich Elkana
# - Sarah
# - Lencer
# - Kennedy
# ==============================================

from pet import Pet

def main():
    my_pet = Pet("Buddy")

    print("Welcome to your virtual pet game!")
    my_pet.get_status()

    my_pet.feed("meat")
    my_pet.get_status()

    my_pet.feed("green vegetables")
    my_pet.get_status()

    my_pet.sleep()
    my_pet.play()
    my_pet.get_status()

    my_pet.train("roll over")
    my_pet.train("fetch")
    my_pet.show_tricks()

    my_pet.get_status()

if __name__ == "__main__":
    main()

