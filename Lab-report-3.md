# Lab Report 3 
## Part 1: Bugs

 1.
  ```
  @Test
  public void testReversedNew() {
    int[] input1 = {1, 2, 3};
    assertArrayEquals(new int[]{3, 2, 1}, ArrayExamples.reversed(input1));
  }
```
 2.
  ```
  @Test
  public void testReversed() {
    int[] input1 = { };
    assertArrayEquals(new int[]{ }, ArrayExamples.reversed(input1));
  }
  ```
  3.
   <img width="1011" alt="Screenshot 2023-11-05 at 6 22 36 PM" src="https://github.com/utkarshlohia/cse15l-lab-reports/assets/62682577/d0187c43-8fc9-420f-945b-b9a4305159ca">
  4.
   Before changing the code

   ```
    static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
```

  After changing the code:
  ```
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length - i - 1];
    }
    return newArray;
  }
 ```
In the original code, the elements of `arr` were not being stored in `newArray`. Rather, the elements of `arr` were being changed to store the elements of the empty array `newArray`. This was fixed by switching the order of the assignment in the code and returning `newArray` instead of `arr`.

## Part 2: Researching Commands

1. The `find -name` command of find is used to find files and driectories of a specific name
   ```
   (base) utkarshlohia@Utkarshs-Air Media % find ../Media -name "Legal_Aid_campaign.txt"
   ../Media/Legal_Aid_campaign.txt
   ```
This command searches for all files named Legal_Aid_campaign.txt in the directory Media and returns the path of those files

  ```
    (base) utkarshlohia@Utkarshs-Air biomed % find ../biomed -name "1471-2296-3-19.txt"     
    ../biomed/1471-2296-3-19.txt
  ```
This command searches for all files named 1471-2296-3-19.txt in the directory Media and returns the path of those files

2. The `find -type` command option is used to search for files based on their type. (Information from ChatGPT)
   ```
   (base) utkarshlohia@Utkarshs-Air technical % find ../technical -type d
    ../technical
    ../technical/government
    ../technical/government/About_LSC
    ../technical/government/Env_Prot_Agen
    ../technical/government/Alcohol_Problems
    ../technical/government/Gen_Account_Office
    ../technical/government/Post_Rate_Comm
    ../technical/government/Media
    ../technical/plos
    ../technical/biomed
    ../technical/911report
   ```
   This command searches for all the directories and returns their path

   ```
   (base) utkarshlohia@Utkarshs-Air technical % find ../technical/government -type f
    ../technical/government/About_LSC/LegalServCorp_v_VelazquezSyllabus.txt
    ../technical/government/About_LSC/Progress_report.txt
    ../technical/government/About_LSC/Strategic_report.txt
    ../technical/government/About_LSC/Comments_on_semiannual.txt
    ../technical/government/About_LSC/Special_report_to_congress.txt
    ../technical/government/About_LSC/CONFIG_STANDARDS.txt
    ../technical/government/About_LSC/commission_report.txt
    ../technical/government/About_LSC/LegalServCorp_v_VelazquezDissent.txt
    ../technical/government/About_LSC/ONTARIO_LEGAL_AID_SERIES.txt
    ../technical/government/About_LSC/LegalServCorp_v_VelazquezOpinion.txt
   ........
   ../technical/government/Media/NJ_Legal_Services.txt
    ../technical/government/Media/Bridging_legal_aid_gap.txt
    ../technical/government/Media/Legal_Aid_campaign.txt
    ../technical/government/Media/Aid_Gets_7_Million.txt
   ```
   This command searches for all the files in the government directory and returns their path. (All file names were not provided since the output was too long)

3. `find -mindepth` starts the search at the minimum depth in the directory tree
   ```
   (base) utkarshlohia@Utkarshs-Air government % find ../government/Alcohol_Problems -type f -mindepth 1
    ../government/Alcohol_Problems/Session2-PDF.txt
    ../government/Alcohol_Problems/Session3-PDF.txt
    ../government/Alcohol_Problems/DraftRecom-PDF.txt
    ../government/Alcohol_Problems/Session4-PDF.txt
   ```
   This command searches for the files with a minimum depth of 1 in the directory tree

   ```
   (base) utkarshlohia@Utkarshs-Air government % find ../government/Alcohol_Problems -type f -mindepth 3
   ```
   This command searches for the files with a minimum depth of 3 in the directory tree
   There is no output since there are no files with a minimum depth of 1 in the directory tree

4. `find -maxdepth` starts the search at the minimum depth in the directory tree
   ```
   (base) utkarshlohia@Utkarshs-Air technical % find ../technical -type d -maxdepth 2
    ../technical
    ../technical/government
    ../technical/government/About_LSC
    ../technical/government/Env_Prot_Agen
    ../technical/government/Alcohol_Problems
    ../technical/government/Gen_Account_Office
    ../technical/government/Post_Rate_Comm
    ../technical/government/Media
    ../technical/plos
    ../technical/biomed
    ../technical/911report
   ```
   This command searches for all directories with a maximum depth of 2 in the directory tree

   ```
   (base) utkarshlohia@Utkarshs-Air technical % find ../technical/government -type f -maxdepth 2
    ../technical/government/About_LSC/LegalServCorp_v_VelazquezSyllabus.txt
    ../technical/government/About_LSC/Progress_report.txt
    ../technical/government/About_LSC/Strategic_report.txt
    ../technical/government/About_LSC/Comments_on_semiannual.txt
    ../technical/government/About_LSC/Special_report_to_congress.txt
    ../technical/government/About_LSC/CONFIG_STANDARDS.txt
    ../technical/government/About_LSC/commission_report.txt
   ............
   ../technical/government/Media/NJ_Legal_Services.txt
    ../technical/government/Media/Bridging_legal_aid_gap.txt
    ../technical/government/Media/Legal_Aid_campaign.txt
    ../technical/government/Media/Aid_Gets_7_Million.txt
   ```
   This command searches for all directories with a maximum depth of 2 in the directory tree (All file names were not provided since the output was too long)


   Source of Information:
   
   
<img width="862" alt="Screenshot 2023-11-05 at 7 41 48 PM" src="https://github.com/utkarshlohia/cse15l-lab-reports/assets/62682577/141a818b-806e-4e31-ae05-b9c38f543e2b">

<img width="721" alt="Screenshot 2023-11-05 at 7 41 58 PM" src="https://github.com/utkarshlohia/cse15l-lab-reports/assets/62682577/7768c6a1-0d7f-435b-b129-7ec03b38405d">


