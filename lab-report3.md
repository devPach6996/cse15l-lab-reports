# Lab Report 3
## Exploring Options For grep command in linux
## 1) `grep -i` 
  * This options allows the user to search throgh a file for a string ignoring the case of the word. For example, if we want to search for "the", it will return all the files
    containing the string "the," "The," "thE," and "tHe." Moreover, it also includes substrings, such as the output will also highlight the word "Theatre."
    * Let's try it in one of the files in `./written_2` directory
    * ![image](https://user-images.githubusercontent.com/122571122/218204918-1146bf29-fb85-4127-ad2a-fa37e5c5175c.png)
    * As we can notice, it highlighed "Art," "heart," and "art" because all of the strings included the word "art."
    * Here is an another example, which indicates that it also includes space. 
    * ![image](https://user-images.githubusercontent.com/122571122/218205664-dd5263a9-69e9-4402-915a-74a7c6369f33.png)
    
    * We can see that there is a word `covers`(it is before "4000 acres") in the file which should be highlighted, but it is not because I passed ` over ` that has two spaces-one before, and the other
    after; therefore, it only found the words, which has one space before, one space after and the word `over` in between. This technique shows a resemblance with `grep -w` command.
## 2) `grep -n`
 * This command finds the word that was passed as parameter and returns its line number with highlighting it. 
   * Let's try it in one of the files in `./written_2` directory
   * If we want to find the line number of the word `Partially` we can do the following:
   * ![image](https://user-images.githubusercontent.com/122571122/218275529-acf06c66-9509-4389-987c-0c8b180d5f2f.png)
   * It tells us that the word `Partially` is in the line 37.
   * But, we can see that it also prints the unnecessary texts, which we don't want. To avoid that, we can use `-o` and `-w` to get the line of a whole word without            printing unwanted text. Let's try to find the word and the line number of `hold`
   *  ![image](https://user-images.githubusercontent.com/122571122/218275627-d7045ec4-48c1-43b7-a0ab-ac50bc907f51.png)

## 3) `grep -l`
 * Sometimes we just want to know the name of the files, which contains the desired string we want. `grep -l` is the best command for that.
   * Let's try it in one of the files in `./written_2` directory
   * If we want to find the file name that contains the string Amsterdam, we can do the following:
   * ![image](https://user-images.githubusercontent.com/122571122/218347863-ef58a4c3-1397-40a7-afe7-af4c36094d86.png)
   * It returned the list of files that contains the string `Amsterdam,` since I used `*` it also found the files containing the desired string from both `berlitz1` and `berlitz2`
   * Here is an another example using patterns:
   * ![image](https://user-images.githubusercontent.com/122571122/218348697-304c8763-0387-436f-ae44-b4c9f78af0ee.png)
   * ![image](https://user-images.githubusercontent.com/122571122/218348714-63e27722-364e-48ec-bb66-ba67f6becded.png)
   * As we can notice, this command is case sensitive unlike `grep -i`, So, we can use grep -i before -l to make it igonore the cases.
   * ![image](https://user-images.githubusercontent.com/122571122/218348857-646008b4-22bc-4939-abeb-83b2fe5cd8d9.png)
   * Here, it ignored the `C` in `computer`
 ## 4) `grep -v`
 * It retunrs the lines that are not containing the string that we pass. 
 * Here is an illustration of the command:
 * ![image](https://user-images.githubusercontent.com/122571122/218349664-77f08ca1-70dd-4e87-8e3a-ebebee78f4f5.png)
 * we can see that we grep on `gr.txt,` it doesn't return anything becuase it doesn't have the line containing `e`
 * Let's  try it with a different input.
 * ![image](https://user-images.githubusercontent.com/122571122/218352103-f0df5a4f-6398-4b92-8d52-e292558b1460.png)
 * As we can see, we don't have any lines that highlight the word `The` because we used `grep -v` on the `IntroEgypt.txt.`
 #THE WEBSITE THAT WAS USED TO FIND THE INFORMATION: https://www.geeksforgeeks.org/grep-command-in-unixlinux/




