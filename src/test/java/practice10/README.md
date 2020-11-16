### Observer Pattern
1. To write a `Person` class, it must have `id`,`name` and `age` attributes, 
 and an `introduce` method.
 We judge whether it is the same person by `id` attribute.
 The `introduce` method returns a string like:
    >My name is Tom. I am 21 years old.
                                                                                                                                                                                                                       
2. Write another `Student` class which inherit from the `Person` class. 
   Besides `name` and `age` attributes, the `Student` class also have `klass` attributes. 
   There is also an `introduce` method,
   The `introduce` method returns a string like:
    >My name is Tom. I am 21 years old. I am a Student. I am at Class 2.

    The `klass` attribute is an `Object` which has `number` and `leader` attribute.
    But the `leader` attibute is `not` in the constructor.

3. When you build an instance of `Student` you need pass
 the `Klass` instance to the constructor of `Student`.
 You can find more details in the test case.
 The `Klass` has an `assignLeader` method, which will take an instance of `Student` as parameter.
 It means to set that student as the monitor of the `Klass`. 
 If the leader of `Klass` is Tom, then Tom calls the `introduce`
  method should return:

    >My name is Tom. I am 21 years old. I am a Student. I am Leader of Class 2.

    If Tom is not the leader, just return the old strings.

4. Klass also has an appendMember method that accepts an instance of Student as parameter.
This means adding a student to the school class.
If the student does not join the class, then when we call the `assignLeader` method , 
the assignment will not succeed, and the method need to print the following sentence:

    >It is not one of us.

    Of course, the `introduce` return the old string as usual. 

5. Write another `Teacher` class which extends the `Person` class.
  In addition to the `id`, `name`, and `age` attributes as `Person` class,
  it also has `classes` attribute, and of course the `introduce` method,
  The `introduce` method should return a string when the `length of classes` is not zero:

    >My name is Tom. I am 21 years old. I am a Teacher. I teach Class 2, 3.

    If the `length of classes` is zero, it should return：

    >My name is Tom. I am 21 years old. I am a Teacher. I teach No Class.

6. Teacher also has an `isTeaching` method, which accepts an instance of `Student` 
   and return `true/false`. 
   As long as the student is in any `klass` of the `classes`, the teacher is teaching him.
   Whether the student is in klass, `Klass` has a method `isIn` to judge. 

7. When a student joins a class, the Teacher will print a sentence like:

    >I am Tom. I know Jerry has joined Class 2.

    When a student becomes the monitor of a class, the Teacher will print a sentence like:

    >I am Tom. I know Jerry become Leader of Class 2.

    All the subclass of `Person` , 
    should call `Person#introduce` method to get following text：

    >My name is Tom. I am 21 years old.
