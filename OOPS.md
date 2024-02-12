OOPS
    Inheretance
        OOPSCONCEPT 

        interface IWildAnimal {

        }

        interface ISocialAnimal {

        }

        abstract class Animal
        {
            public abstract string Speak(); 
        } 

        class Deer : Animal, IWildAnimal, ISocialAnimal {

            public override string Speak() {
                return "Abc";
            } 

        }


        class Dog : Animal 
        {
            public override string Speak() {
                return "Bark";
            } 

            public bool HasTail()
            {
                return true;
            } 
        }

        class GermanShepard : Dog {
            public bool CanLiveInCold() {
                return false;
            }

        }

        class B {
            protected int minus(int a, int b) {
                return a - b;
            }

            intenal protected int Add(int a, int b, int c) {

            }

            protected virtual bool ConfirmInventory(Cart cart) {
                return true;
            }

            internal virtual bool ConfirmPayment(Cart cart) {
                return true;
            }

            public bool OrderPlacement(Cart cart)
            {
                ConfirmInventory(cart);
                ConfirmPayment(cart);
                PlaceOrder(cart);
                DeductInventory(cart);
            }

        }

        main() {
            B b = new B();
            b.OrderPlacement();
            b.ConfirmPayment();
            
            Animal a = new Animal(); //Compile time error Abstarct class instance can not be create
            
            //&12323
            Animal dog = new Dog(); 
            dog.Speak();
            dog.HasTail(); // Compile Time error Type Animal does not contain function HasTail
            Dog d1 = dog as Dog;
            d1.HasTail();

            Dog d = new GermanShepard(); 
            Animal a = new GermanShepard();

            GermanShepard g1 = new Dog(); // Invalid 
            g1.CanLiveInCold();

            ISocialAnimal deer1 = new Deer();
            IWildAnimal deer2 = new Deer();
            Animal deer3 = new Deer();

            // any parent class can be use as a reference for Child class object.
        }

        Memory {
            Allocation
            12323 Dog {
               Speak() 
               HasTail()
            }

        }

        class D : B {
            private int Add(int a, int b, int c, int d) {
                return Add(a, b, c) + d;
            }
        }

        class E: D {
            private int Add(int a, int b) {
                return Add(a,b,0); //compile time error
            }
        }

        AdvancedConcept
         class A : B {
            private int minus(int a, intb, int c) {
                return minus(a,b) - c;
            }

            private int Add(int a, int b, int c, int d) {
                return Add(a, b, c) + d; // compile time error

            }
        }

        class C : A {

        }

    Polymorpism
        Method Overriding/ runtime binding 
        class Animal {
            public virtual string Sound() {
                return "make sound";
            }
        }

        class Dog : Animal {
            public override string Sound() {
                return "Bow wow";
            }

            public bool HasTail() {
                return true;
            }
        }

        class GermanShephard : Dog {
            public new bool HasTail() { //Method Hiding 
                return false;
            }
        }

        main() {
            Animal dog = new GermanShephard();
            dog.Sound(); //it will return "Bow wow"
            
            Dog dog1 = dog as Dog;
            dog1.HasTail(); //It will return true

            GermanShepard gs = dog1 as GermanShepard;
            gs.HasTail(); //It will return false

        }

        MemoryAllocation {
            GermanShepard {
                Sound() => "Bow wow"
                Dog.HasTail() => true
                HasTail() => false
            }
        }

        Method Overloading / compiletime binding 

        class Math {
            public int Add(int a, int b)
            {
                return a+b;
            }

            public int Add(int a, int b , int c) 
            {
                return Add(a,b) +c;
            }
        }

        class AdvanceMath : Math {
            public int Add(int a, int b, int c, int d) {
                return Add(a,b) + Add(c,d)
            }
        }

        main() {
            AdvanceMath math = new AdvanceMath();
            math.Add(1,2);
            math.Add(1,2,3);
            math.Add(1,2,3,4);
        }



    Encapsulation
        private 
        protected 
        public

        internal protected  (Assembly)
        internal (Assembly)
        
    Abstraction
        Abstarct class in c# which can have Abstract methods

    OopsConcept (Library)
     class ABC {
        internal protected int Add(int a, int b)  {
            return a+b
        }

     }


    AdvancedConcept
        References
          OopsConcept
