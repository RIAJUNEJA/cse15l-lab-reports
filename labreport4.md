# Lab Report 4

Here are the steps I am supposed to demonstrate:

> Step 4 - Log into ieng6

![image](https://user-images.githubusercontent.com/122485765/221482822-38e55ec6-5749-4f7a-b2d0-8401db9c38eb.png)

**keys pressed** : ssh cse15lwi23akh@ieng6.ucsd.edu ```<enter>``` ```*password*``` ,```<enter>```
  
 This my first time using this command so I had to manually enter details. Manually entered password when prompted.
  
> Step 5 - Clone your fork of the repository from your Github account
  
 ![image](https://user-images.githubusercontent.com/122485765/221483992-48508fc6-4066-4c44-b803-17433b5f26ee.png)

  **keys pressed** : ```git clone``` ```<Command+V>``` ```<enter>```
  
  I copied the link to my fork and pasted in the terminal using ```command + V``` shortcut since I am on a mac.
  
  
  >Step 6 - Run the tests, demonstrating that they fail
  
  <img width="1106" alt="image" src="https://user-images.githubusercontent.com/122485765/221486259-3e9545bc-f23f-430a-82e5-c20917f1f5e8.png">

  **keys pressed** : ```cd lab7 <enter> <ls> <up><up><up><up><up><enter> <up><up><up><up><up><up><enter> <Command+V>```
  
  I entered lab 7 directly using cd command. I used ls to see where my path is currently. My ```.:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java``` command was 5 up so I just used up commands. Similarly my ```.:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore``` command was 6 up so I used up keys. 
  I had copied the Tester File's name to my keyboard and used ```<Command+V>``` to copy it.
  
  >Step 7 - Edit the code file to fix the failing test
  
  ```
  // Takes two sorted list of strings (so "a" appears before "b" and so on),
  // and return a new list that has all the strings in both list in sorted order.
  static List<String> merge(List<String> list1, List<String> list2) {
    List<String> result = new ArrayList<>();
    int index1 = 0, index2 = 0;
    while(index1 < list1.size() && index2 < list2.size()) {
      if(list1.get(index1).compareTo(list2.get(index2)) < 0) {
        result.add(list1.get(index1));
        index1 += 1;
      }
      else if(list1.get(index1).compareTo(list2.get(index2)) == 0){
        result.add(list1.get(index1));
        result.add(list2.get(index2));
        index1 += 1;
        index2+=1;
      }
      else {
        result.add(list2.get(index2));
        index2 += 1;
      }
  
  ```
  I fixed this part of the code to ensure equal elements are being considered and both are being added to the resultant list.
                                                            
 > Step 8 - Run the tests, demonstrating that they now succeed
  
  ![image](https://user-images.githubusercontent.com/122485765/221495332-46e7bce4-8f55-4894-a870-960eb90fa3ec.png)
  
  **keys pressed** : ```<up><up><enter> <up><up><enter>```
  
  My compile commands had been used recemtly and therefore I just needed to use the up buttons.
  
  > Step 9 - Commit and push the resulting change to your Github account
  
  **keys pressed**: ```git command -m Li<tab> Lis<tab>```
  
  To commit, I used git `command -m` and committed the file to ListExamples.java. I used tab to autocomplete and save time.

                                                         
  
