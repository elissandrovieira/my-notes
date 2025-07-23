# Overview

For a long time, learning Object-Oriented Programming felt like eating soup with a fork.  
I could write code. I could follow tutorials. But when it came to concepts like **inheritance**, **polymorphism**, or **interfaces**, nothing really made sense.

The truth is: I don’t learn well through abstract theory. I learn by **visualizing**, by **connecting ideas to the real world**.

That’s when I started building analogies — and suddenly, OOP started to click.

If you’ve also struggled with these concepts, maybe these analogies can help you too.

**To my future self**: read this again if you ever get lost in OOP.

# Classes

A class is like a mold or a recipe to create objects that represent things from the real world or abstract concepts.  

It defines which characteristics (attributes) and behaviors (methods) those objects will have. These are the main elements of a class:  
- Attributes are variables defined inside the class.
- Methods are functions created inside the class.  

If you already know [[C]], you can think of a class as something similar to a [[Struct]], but much more powerful because, besides holding data, it can also have functions that operate on that data.

**Example:**
You can create a class called **Car**. All the cars have attributes like brand, model, color, etc. A car also has methods, like drive forward, reverse, brake, turn on the headlight, etc.

# Objects

Objects are the "real things" that a class creates, like real-world objects.  
Your iPhone is yours, right? But it’s still an iPhone — an Apple product.

Objects are like that: they are instances of a class.  
Your phone is the object, and the iPhone itself is the instantiated class.

# Interfaces

The interfaces are models to define witch methods a class should have, but without implementing the method.

It’s like when we were toddlers and wanted to ride the big roller coaster, but we weren’t tall enough. To join the "Roller Coaster Riders" group, you need to meet a requirement — like being at least 1.20 meters tall. Your toddler self had everything else, but was missing that one key requirement.

In programming terms:
- The **interface** is the height requirement sign.
- Your class can only "join" (implement) that group if it provides all the required methods.
- If it’s missing one? You’re not allowed in.

# Inheritance

In general, this should be a simple concept. But somehow, it never made sense to me.  
So here’s the explanation that finally helped me understand it.

**Inheritance** is like the characteristics you get from your parents.  In my case, asthma and all kinds of respiratory diseases.

In OOP terms, my father is a class whit attributes like:
``` java
String diseaseType = "respiratory";
String diseaseName = "asthma";
```

And methods like:
``` java
sneeze();
runnyNose();
```

I'm a child class derived from my father class.  
Because of that, I **inherit** all the attributes and methods he has.

# Polymorphism

When I finally understood polymorphism, I was really excited — because in the past, this concept just didn’t make any sense to me.

It’s like a **USB port** on your PC. It’s the same port for all devices you connect, but it behaves differently depending on the device.

- If you connect a memory drive (like a pen drive), you can access data.
- If you connect a USB headphone, you can listen to music.
- And if the device doesn’t have any special function over USB, it will simply charge.

Basically, that’s the idea. Child classes can have **different behaviors for the same method**. You could have a parent class with a method, and the child classes override that method to do something else. Like this:

``` Java
class UsbDevice {
    void connection() {
        System.out.println("Charging...");
    }
}

class MemoryDrive extends UsbDevice {
    @Override
    void connection() {
        System.out.println("Accessing data...");
    }
}

class Headphone extends UsbDevice {
    @Override
    void connection() {
        System.out.println("Listening to music...");
    }
}
```

It is the **override polymorphism**. There are some other types, but the concept are similar to this. Look at these others:

- **Overload**
	- This happens when a class has **two or more methods with the same name**, but each one has **different parameters**.
	- It’s like USB-A and USB-C ports. They **serve the same purpose**, but the difference lies in their capabilities. For example, USB-C can transmit video, while USB-A can’t. 
	- So you know **which type of connection it is** by checking what the device supports — just like how the method version is chosen based on the parameters.

``` java
class UsbDevice {
    void connection() {
        System.out.println("Charging...");
    }
     void connection(String videoTransmission) {
        System.out.println("Watching " + videoTransmission + "...");
    }
}
```

- **Parametric**
	- This is when you write code that works for **any data type**, using **generics**.
	- It’s like having a **universal socket** that can accept any plug. You don’t need to know the exact type in advance — it adapts.

``` java
class UsbPort<T> {
    T connectedDevice;
    
    void connect(T device) {
        this.connectedDevice = device;
        System.out.println("Connected: " + device.toString());
    }
}
```

Now, you can create:

``` java
UsbPort<String> port1 = new UsbPort<>();
port1.connect("Webcam");

UsbPort<Integer> port2 = new UsbPort<>();
port2.connect(12345);
```

- **Subtype**
	- - Do you remember the USB devices from the first example? The memory drive and the headphone?
    - Imagine you bought a new laptop, but now you need some accessories to improve your experience.
    - You go to a store and ask the salesperson:
        - _"Where are the USB devices?"_
    - You're not buying just any USB device — you’re looking for a memory drive and a headphone.  
        Even so, you refer to all of them as “USB devices”.
    - In **subtype polymorphism**, the object is created as a child class, but **stored as the parent type**.

``` java

UsbDevice penDrive = new MemoryDrive();
penDrive.connection();  // "Accessing data..."

UsbDevice airPods = new Headphone();
penDrive.connection();  // "Listening to music..."
```

- **Coercion**
	- This happens when the language **automatically converts a value to match the expected type**.
	- Think of it like this: you have a USB-C port, but your device is USB-A. You can still plug it in using an adapter.
	- In the same way, you might pass an `int` value to a method that expects a `double`. The programming language will **coerce** the value for you.
	
``` java
void connectToPort(double voltage) {
    System.out.println("Connecting with voltage: " + voltage);
}

connectToPort(5); // You passed an int (USB-A), but it was converted to double (USB-C)
```

# Encapsulation

Imagine you're at a restaurant. You want to place an order. You look at the menu, call the waiter, and ask about a pasta.

You **don’t see how the pasta is made**, and you definitely **don’t know the "secret ingredients"** being used.

This is **encapsulation**:
- **The restaurant is a class** — it provides a service, but you don’t see its internal process.
- **How the pasta is made is a private attribute** — it’s hidden from you, and you’re **not allowed** to access or change it directly.
- **The menu is like a getter** — it gives you **access to selected internal details** (like the dish name or description) in a safe, controlled way.
- **The waiter is like a setter** — you ask him to **set values** (your order), and he communicates safely with the kitchen (the private internals).

``` java
public class Customer {
    public static void main(String[] args) {
        ItalianRestaurant restaurant = new ItalianRestaurant();
        
        // Look at the menu
        System.out.println("Menu: Today's pasta is " + restaurant.getPastaType());

        // Make your order
        restaurant.setPastaType("Fettuccine");

        // Enjoy your dish
        restaurant.serveDish();

        // Try to order something they don't serve
        restaurant.setPastaType("Cup Noodles");  // Not allowed!
    }
}
```

## What’s the point?

Encapsulation means **you interact with the system through a clean, public interface**,  
while the internal logic and data are **protected and hidden** — just like a real restaurant.

## Without encapsulation:

Imagine a customer who walks into the kitchen, grabs the pot, and dumps ketchup on the chef’s carbonara. That’s chaos — both in real life and in code.

# Conclusion

This was my two cents on Object-Oriented Programming.  
My goal here was to share the way I see things and try to simplify a concept that can be confusing — especially if, like me, you struggle with abstract ideas.

I hope it was helpful. Good luck with your studies — and buddy, don’t give up. It eventually clicks.

