# Python-OOP
# Assignment 1: Design Your Own Class
class Smartphone:
    def __init__(self, brand, model, price):
        self.__brand = brand  # Private attribute
        self.__model = model  # Private attribute
        self.price = price    # Public attribute

    # Getter for brand
    def get_brand(self):
        return self.__brand

    # Setter for brand
    def set_brand(self, brand):
        self.__brand = brand

    # Method to display smartphone details
    def details(self):
        return f"Brand: {self.__brand}, Model: {self.__model}, Price: ${self.price}"

class Smartwatch(Smartphone):  # Inheriting from Smartphone
    def __init__(self, brand, model, price, features):
        super().__init__(brand, model, price)  # Call parent constructor
        self.features = features              # Unique attribute for Smartwatch

    # Overriding details() method
    def details(self):
        return f"{super().details()}, Features: {', '.join(self.features)}"


# Create objects
phone = Smartphone("Apple", "iPhone 14", 999)
watch = Smartwatch("Samsung", "Galaxy Watch 5", 299, ["Heart Rate Monitor", "GPS", "Waterproof"])

# Access details
print(phone.details())  # Brand: Apple, Model: iPhone 14, Price: $999
print(watch.details())  # Brand: Samsung, Model: Galaxy Watch 5, Price: $299, Features: Heart Rate Monitor, GPS, Waterproof

# Encapsulation example
phone.set_brand("OnePlus")
print(phone.get_brand())  # OnePlus


# Activity 2: Polymorphism Challenge
class Vehicle:
    def move(self):
        pass  # Placeholder for polymorphism

class Car(Vehicle):
    def move(self):
        print("Driving 🚗")

class Plane(Vehicle):
    def move(self):
        print("Flying ✈️")

class Boat(Vehicle):
    def move(self):
        print("Sailing 🚤")

# Create objects
vehicles = [Car(), Plane(), Boat()]

# Demonstrate polymorphism
for vehicle in vehicles:
    vehicle.move()

