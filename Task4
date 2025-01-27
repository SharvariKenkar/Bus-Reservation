import java.util.*;

class Bus {
    private String busNo;
    private String source;
    private String destination;
    private int capacity;
    private int availableSeats;
    private double price;

    public Bus(String busNo, String source, String destination, int capacity, double price) {
        this.busNo = busNo;
        this.source = source;
        this.destination = destination;
        this.capacity = capacity;
        this.availableSeats = capacity;
        this.price = price;
    }

    public String getBusNo() {
        return busNo;
    }

    public String getSource() {
        return source;
    }

    public String getDestination() {
        return destination;
    }

    public int getCapacity() {
        return capacity;
    }

    public int getAvailableSeats() {
        return availableSeats;
    }

    public double getPrice() {
        return price;
    }

    public void bookSeats(int numSeats) {
        if (numSeats <= availableSeats) {
            availableSeats -= numSeats;
            System.out.println("Seats booked successfully!");
        } else {
            System.out.println("Insufficient seats available.");
        }
    }

    public void cancelSeats(int numSeats) {
        availableSeats += numSeats;
        System.out.println("Seats cancelled successfully!");
    }

    public String toString() {
        return "Bus No: " + busNo + "\n" +
                "Source: " + source + "\n" +
                "Destination: " + destination + "\n" +
                "Capacity: " + capacity + "\n" +
                "Available Seats: " + availableSeats + "\n" +
                "Price: " + price;
    }
}

class BusReservationSystem {
    private List<Bus> buses;

    public BusReservationSystem() {
        buses = new ArrayList<>();
    }

    public void addBus(Bus bus) {
        buses.add(bus);
    }

    public void displayBuses() {
        for (Bus bus : buses) {
            System.out.println(bus);
            System.out.println("--------------------");
        }
    }

    public Bus searchBus(String source, String destination) {
        for (Bus bus : buses) {
            if (bus.getSource().equals(source) && bus.getDestination().equals(destination)) {
                return bus;
            }
        }
        return null;
    }

    public void bookTickets(String source, String destination, int numSeats) {
        Bus bus = searchBus(source, destination);
        if (bus != null) {
            bus.bookSeats(numSeats);
        } else {
            System.out.println("No buses found for the given source and destination.");
        }
    }

    public void cancelTickets(String busNo, int numSeats) {
        for (Bus bus : buses) {
            if (bus.getBusNo().equals(busNo)) {
                bus.cancelSeats(numSeats);
                return;
            }
        }
        System.out.println("Bus not found.");
    }
}

public class Main {
    public static void main(String[] args) {
        BusReservationSystem system = new BusReservationSystem();

        // Add buses to the system
        system.addBus(new Bus("B1", "Delhi", "Mumbai", 50, 1000.0));
        system.addBus(new Bus("B2", "Bangalore", "Chennai", 40, 800.0));
        system.addBus(new Bus("B3", "Kolkata", "Delhi", 60, 1200.0));

        // Display all buses
        system.displayBuses();

        // Search for a bus
        Bus bus = system.searchBus("Delhi", "Mumbai");
        if (bus != null) {
            System.out.println("Bus found:");
            System.out.println(bus);
        } else {
            System.out.println("No buses found.");
        }

        // Book tickets
        system.bookTickets("Delhi", "Mumbai", 10);

        // Cancel tickets
        system.cancelTickets("B1", 5);

        // Display all buses again
        system.displayBuses();
    }
}
