# Base class representing general fashion
class Fashion:
    def __init__(self, brand, style, season):
        self.brand = brand              # Public attribute
        self._style = style             # Protected attribute
        self.__season = season          # Private attribute

    def describe(self):
        return f"{self.brand} offers a {self._style} collection perfect for the {self.__season} season."

    def get_season(self):
        # Encapsulation: Accessing private attribute via method
        return self.__season

    def set_season(self, new_season):
        self.__season = new_season

    def wear(self):
        return f"You look stylish in your {self.brand} outfit!"

# Subclass representing a specific type of fashion - Streetwear
class Streetwear(Fashion):
    def __init__(self, brand, style, season, hype_level):
        super().__init__(brand, style, season)
        self.hype_level = hype_level

    # Polymorphism: overriding the base class method
    def wear(self):
        return f"Rocking {self.brand} streetwear with a hype level of {self.hype_level}!"

# Subclass representing a different fashion type - Haute Couture
class HauteCouture(Fashion):
    def __init__(self, brand, style, season, designer):
        super().__init__(brand, style, season)
        self.designer = designer

    def wear(self):
        return f"Gracing the runway in a {self.brand} piece designed by {self.designer}."

# Example usage
outfit1 = Streetwear("Supreme", "urban", "spring", 10)
outfit2 = HauteCouture("Chanel", "elegant", "winter", "Karl Lagerfeld")

print(outfit1.describe())
print(outfit1.wear())
print(outfit2.describe())
print(outfit2.wear())
# Class--fashion

Polymorphism Challenge
# Base class
class Vehicle:
    def move(self):
        raise NotImplementedError("Subclasses must implement this method.")

# Subclass: Car
class Car(Vehicle):
    def move(self):
        print("Driving")

# Subclass: Plane
class Plane(Vehicle):
    def move(self):
        print("Flying")

# Subclass: Boat
class Boat(Vehicle):
    def move(self):
        print("Sailing")

# Subclass: Bicycle
class Bicycle(Vehicle):
    def move(self):
        print("Pedaling")

# Subclass: Train
class Train(Vehicle):
    def move(self):
        print("Chugging along")

# Function that takes any vehicle and calls move()
def travel(vehicle):
    vehicle.move()

# Example usage
vehicles = [Car(), Plane(), Boat(), Bicycle(), Train()]

for v in vehicles:
    travel(v)
