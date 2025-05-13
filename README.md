# Define the Smartphone class
class Smartphone:
    def __init__(self, brand, model, os, battery_life):
        self.brand = brand
        self.model = model
        self.os = os
        self.battery_life = battery_life
        self.power_status = False  # Initially off

    # Method to power on the smartphone
    def power_on(self):
        if not self.power_status:
            self.power_status = True
            print(f"{self.model} is now powered on!")
        else:
            print(f"{self.model} is already on!")

    # Method to power off the smartphone
    def power_off(self):
        if self.power_status:
            self.power_status = False
            print(f"{self.model} is now powered off!")
        else:
            print(f"{self.model} is already off!")

    # Method to display the status of the smartphone
    def display_status(self):
        power = "on" if self.power_status else "off"
        print(f"{self.model} ({self.os}) is currently {power} with {self.battery_life}% battery left.")

# Define the Vehicle class (base class)
class Vehicle:
    def move(self):
        pass  # We'll define this method in the child classes

# Define the Car class (inherits from Vehicle)
class Car(Vehicle):
    def move(self):
        print("Driving 🚗")

# Define the Plane class (inherits from Vehicle)
class Plane(Vehicle):
    def move(self):
        print("Flying ✈️")

# Test the Smartphone class
phone1 = Smartphone("Apple", "iPhone 14", "iOS", 85)
phone2 = Smartphone("Samsung", "Galaxy S21", "Android", 45)

# Test the methods of the Smartphone class
phone1.display_status()
phone1.power_on()
phone1.display_status()
phone1.power_off()
phone1.display_status()

# Test the Vehicle polymorphism
car = Car()
plane = Plane()

# Test the move method
car.move()   # This will print "Driving 🚗"
plane.move() # This will print "Flying ✈️"
