package Java1Lesson6HW;

import Java1Lesson6HW.animals.Animal;
import Java1Lesson6HW.animals.Cat;
import Java1Lesson6HW.animals.Dog;

public class MainApp {
    public static void main(String[] args) {

        Cat[] cats = new Cat[5];
        Cat cat1 = new Cat("Barsik", "White", 5, 0, 130, 5);
        Cat cat2 = new Cat("Versace", "White", 6, 2, 200, 5);
        Cat cat3 = new Cat("Simba", "Red", 3, 100, 600, 50);
        Cat cat4 = new Cat("Nala", "Red", 3, 80, 580, 45);
        Cat cat5 = new Cat("Mufasa", "Red", 7, 90, 350, 55);
        cats[0] = cat1; cats[1] = cat2; cats[2]=cat3; cats[3]=cat4; cats[4]=cat5;

        Dog[] dogs = new Dog[3];
        Dog dog1 = new Dog ("Bobik", "Black", 2, 55, 200, 3, 10);
        Dog dog2 = new Dog ("Keiko", "Red", 3, 100, 600, 2, 15);
        Dog dog3 = new Dog ("Sky", "Black", 6, 110,300, 6,20);
        dogs[0] = dog1; dogs[1]=dog2; dogs[2] = dog3;

        Animal animal1 = new Horse("Apple", "Spotted", 3, 500, 1000, 50);


        Bowl bowl = new Bowl(100);
        bowl.info();
        System.out.println();
        for (int i=0; i< cats.length; i++) {
            cats[i].eat(bowl);
        }

        System.out.println();
     for (int i=0; i< cats.length; i++) {
      cats[i].info();
      cats[i].swim(100);
      cats[i].run(500);
     }
       System.out.println();
        cats[4].displayId();
        System.out.println();
     for (int i=0; i< dogs.length; i++) {
      dogs[i].info();
      dogs[i].swim(100);
      dogs[i].run(500);
     }
        System.out.println();
        dog2.displayId();
        System.out.println();

        ((Horse)animal1).info();

        if(animal1 instanceof Horse){
            ((Horse) animal1).race();
        }
        animal1.swim(100);
        animal1.run(500);
        System.out.println();
        animal1.displayId();
        System.out.println();
    }
}

