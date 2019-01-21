# CSCI 380-04: Assignment 1 - Due by 11:59 PM, Feb 19th, 2019
* * * 

	 This assignment is meant to introduce you to git, Android Studio, and Java fundamentals.
	 Complete each part of the assignment as separate git commits. Any assignment that's completed, 
	 but uses only one giant commit will have 10% taken off. If you don't already have 
	 Android Studio and git set up on your computer, follow the instructions here before continuing: 
	 - https://developer.android.com/training/basics/firstapp/
	 - https://git-scm.com/book/en/v2/Getting-Started-Installing-Git
	 
# Part 0 - Reading
Read the following before attempting this assignment. Make sure to follow the naming convention below in 
your assignments. You will be deducted 1% for each naming convention violation.
+ [https://leanpub.com/aprimeronjava/read](https://leanpub.com/aprimeronjava/read)
+ [https://google.github.io/styleguide/javaguide.html#s5-naming](https://google.github.io/styleguide/javaguide.html#s5-naming)

# Part 1 - Github Setup - 5%
+ Create a Github account
+ Once your Github account is created, make sure to authenticate with an SSH key (see [https://help.github.com/articles/connecting-to-github-with-ssh/](https://help.github.com/articles/connecting-to-github-with-ssh/)).
+ Create a new **private repo** called `assignment1` on your personal Github account (see [https://help.github.com/articles/creating-a-new-repository/](https://help.github.com/articles/creating-a-new-repository/)). Don't initialize with a readme, since you'll just be importing this
existing project to your new repo.
+ In terminal, cd into a directory where you'd like to keep your projects.
+ Clone this repo using the following command:
    + `git clone https://github.com/bhargman/assignment1.git`
+ Once your repo is cloned, `cd` into it using terminal, and use the following commands to set the remote to your new repo and push your project:
    + `git remote set-url origin git@github.com:[yourGithubUserName]/assignment1.git`
    + `git push -u origin master`
+ Add me as a collaborator (username : `bhargman`) to your private repo (see [https://help.github.com/articles/inviting-collaborators-to-a-personal-repository/](https://help.github.com/articles/inviting-collaborators-to-a-personal-repository/)).
    + **If you don't do this step, I'll have no way of grading your assignment**

# Part 2 - Android Studio - 5%
+ Import your `assignment1` repo into Android Studio
+ In the main Android Studio window, tap on "Open an existing Android Studio project"
+ Browse to your `assignment` folder and select to open it
+ Android Studio will now load the project and you should be able to do the rest of this assignment

# Part 3 - Primitives - 10%
Update `Primitives.java` to include the following:
+ `private` fields for every type of primitive.
+ Constructor with parameters to initialize every primitive field.
+ Update the `print()` method in `Primitives.java` that will print each primitive value on a new line, with the format `"variableName : value"`
+ Add a main method to `Primitives.java` that creates an instance of `Primitives` with name `primitives`, and calls `primitives.print()`.

# Part 4 - Arrays - 30 %
+ Update the constructor in `Arrays.java` to initialize the `squares` array with the first 10 *even* squares (exclude 0).
+ Update the `printSquaresBackward()` method in `Arrays.java` to print each value of the `squares` array in backwards order.
+ Add a main method to `Arrays.java` that creates an instance of `Arrays` with name `arrays`, and calls `primitives.printSquares()`.

# Part 5 - Classes - 50%
+ Create a new `package` in `com.csci38004.assignment` called `shapes`.
+ All work for this part should be done in the `shapes` package.
+ Create a new `interface` called `Shape`.
+ Add `double area()` and ` double perimter()` methods to the `Shape` interface.
+ Create two classes called `Circle` and `Rectangle` which implement `Shape`.
+ Add reasonable fields to the `Circle` and `Rectangle` classes which will allow you to calculate the area and perimeter of each shape.
+ Add constructors to `Circle` and `Rectangle` so you can initialize your fields.
+ Implement the `area()` and `perimeter()` methods for `Circle` and `Rectangle`.
+ Create an interface called `Shape3D`.
+ Add `double volume()` method to `Shape3D`.
+ Create a class called `Cyclinder` which extends `Circle` and implements `Shape3D`.
+ Add and initialize any required fields that you may need to calculate a cylinder's volume.
+ Keep in mind that the `Cylinder` class will have access to its parent (`Circle`) class' methods. Use this to your advantage to implement the `volume()` method.
+ Create a class named `ShapeRunner` with the following main method:
```
public static void main(String[] args) {
    Shape circle = new Circle(2.0);
    Shape rectangle = new Rectangle(4.0, 2.0);
    Shape3D cylinder = new Cylinder(4.0, 1.0);

    System.out.println("Circle:");
    System.out.println("Area: " + circle.area() + ". Perimeter: " + circle.perimeter());
    System.out.println("\nRectangle:");
    System.out.println("Area: " + rectangle.area() + ". Perimeter: " + rectangle.perimeter());
    System.out.println("\nCylinder:");
    System.out.println("Volume: " + cylinder.volume());
}
```
+ Notice how the shapes are declared with their interfaces instead of their concrete types. This allows for more flexibility when
trying to extend an application, but also makes sure that you are able to only access methods on the interface's contract. Feel free
to play around with different values to test your implementations, but when submitting your final assignment, make sure to leave this
`main()` method as written here.