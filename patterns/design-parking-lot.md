# Design Parking Lot

## Problem Statement

Implement a parking lot system that supports different vehicle types and parking spaces.

## Key Concepts

- Factory Pattern: Create parking spaces based on vehicle type.
- Extensibility: Easy to add new vehicle or parking space types.

## Example (Java)

```java
interface Vehicle {
    String getType();
}
class Car implements Vehicle {
    public String getType() { return "Car"; }
}
class Bike implements Vehicle {
    public String getType() { return "Bike"; }
}
interface ParkingSpace {
    void park(Vehicle vehicle);
}
class CarParkingSpace implements ParkingSpace {
    public void park(Vehicle vehicle) {
        System.out.println("Car parked");
    }
}
class BikeParkingSpace implements ParkingSpace {
    public void park(Vehicle vehicle) {
        System.out.println("Bike parked");
    }
}
class ParkingSpaceFactory {
    public static ParkingSpace getParkingSpace(Vehicle vehicle) {
        if (vehicle.getType().equals("Car")) return new CarParkingSpace();
        else if (vehicle.getType().equals("Bike")) return new BikeParkingSpace();
        throw new IllegalArgumentException("Unknown vehicle type");
    }
}
```

## When to Use

- Parking management systems
- Systems with multiple types of resources

## Advantages

- Centralized creation logic
- Easy to extend

## Disadvantages

- Can introduce extra classes
- May be overkill for simple cases
