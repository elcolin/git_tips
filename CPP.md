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
