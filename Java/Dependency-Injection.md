❌ Hard-Coded Dependency Example

// Engine interface
interface Engine {
    void start();
}

// A concrete engine
class PetrolEngine implements Engine {
    public void start() {
        System.out.println("Petrol engine started");
    }
}

// Car class with hard-coded dependency
class Car {
    private Engine engine;

    public Car() {
        // Hard-coded dependency
        engine = new PetrolEngine();
    }

    public void drive() {
        engine.start();
    }
}

✅ Dependency Injection Example

// Engine interface
interface Engine {
    void start();
}

// A concrete engine
class PetrolEngine implements Engine {
    public void start() {
        System.out.println("Petrol engine started");
    }
}

// Car class with dependency injection
class Car {
    private Engine engine;

    // Constructor injection
    public Car(Engine engine) {
        this.engine = engine;
    }

    public void drive() {
        engine.start();
    }
}

// Usage
public class Main {
    public static void main(String[] args) {
        Engine engine = new PetrolEngine(); // You decide which engine to inject
        Car car = new Car(engine);
        car.drive();
    }
}


🟢 Key Difference:

In the first version, Car creates the PetrolEngine itself — it's tightly coupled.
In the second version, Car receives the engine from outside — loosely coupled and flexible.
