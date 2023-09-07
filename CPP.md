# CPP
## Coplien Form
    class T
    {
        public:
            T (); // Constructeur par défaut
            T (const T&); // Constructeur de recopie
            ~T (); // Destructeur éventuellement virtuel
            T &operator=(const T&); // Operator d'affectation
    };
If you have **circular dependencies** (per example, Class A involves Class B objects and Class B involves Class A), you need to include the class as such:

    #include "AnotherFile.hpp"

    class OtherClass;
## Attributes
### public
Members (variables and functions) declared as **public** are accessible from anywhere, both inside and outside the class.
### private
Members declared as **private** are only accessible within the class that defines them.
### protected
Members declared as **protected** are accessible within the class that defines them and within derived classes (cf inheritance).

## References
Use references when you want to avoid copying data and work on the original object:

    void modifyValue(int& x) {
        x = x * 2;
    }
## const
### const variables
Use const when you want to guarantee the object won't be modified.

    void printValue(const int& x) {
        // x cannot be modified within this function
        std::cout << x << std::endl;
    }

### const function members
Use const to indicate that the function won't modify the object, allowing you to call you function on const objects.

    class MyClass {
    public:
        int getValue() const {
            return data;
        }
    private:
        int data;
    };
    
## exception
### basic exception
    class BasicException : public std::exception
    {
        const char *what() const throw()
        {
            return ("Basic Exception");
        }
    };

### exception with custom message

    class NewException : public std::exception
    {
        private:
            const char  *msg;
        public:
            NewException(const char *msg) : msg(msg) {}
            virtual const char* what() const throw()
            {
                return msg;
            }
    };
## virtual
**virtual** keyword is used for polymorphism. Polymorphism allows objects of different classes that inherit from a common base class to be treated as objects of the base class. It enables you to write code that can work with objects of different derived classes through pointers or references to the base class.

    class Shape {
    public:
        virtual void draw() {
            // Base class implementation
        }
    };

    class Circle : public Shape {
    public:
        void draw() override {
            // Derived class implementation
        }
    };

    int main() {
        Shape* shapePtr;
        Circle circle;

        shapePtr = &circle;
        shapePtr->draw(); // Calls the draw() method of Circle
    }

### Pure method
If a class contains a **pure virtual function** it will create a **Abstract class**.

    class AbstractClass {
    public:
        virtual void pureVirtualFunction() = 0; // Pure virtual function
    };
Which means that AbstractClass cannot exist by itself, it needs to be inherited in a derived class that will define pureVirtualFunction().

## Inheritance
Inheritance allows a class to have a parent class. It will inherit all attributes from that said class. Functions defined with the virtual keyword can be overriden and pure virtual function need to be implemented.

    class ConcreteClass : public AbstractClass {
    public:
        void pureVirtualFunction() override {
            // Provide an implementation for the pure virtual function
        }
    };
