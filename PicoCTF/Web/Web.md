1)Includes

![image](https://user-images.githubusercontent.com/95273832/181788306-581441ad-e01a-4f6b-929c-31fe4b03441e.png)

Solution

hint:Is there more code than what the inspector initially shows? So,I check code of website and open file "style.css" and "script.js".I get 2 path of flag

![image](https://user-images.githubusercontent.com/95273832/181788342-8bb121e3-21ff-4693-a1fb-3c1691ea8d53.png)

Flag:picoCTF{1nclu51v17y_1of2_f7w_2of2_b8f4b022}

2)Inspect HTML

![image](https://user-images.githubusercontent.com/95273832/181788410-b4d91a18-8aed-4f1f-addd-b427fefb1961.png)

Solution As title,we just need check code of website

![image](https://user-images.githubusercontent.com/95273832/181788438-3f274946-e979-4983-bfcc-460092990f47.png)

Flag:picoCTF{1n5p3t0r_0f_h7ml_fd5d57bd}

3)Local Authority

![image](https://user-images.githubusercontent.com/95273832/181788504-173c9fc8-9e85-4c3b-8706-317a25549c9b.png)

Solution 
I tried Username:admin & Password:admin123 =>login faile After,i see source code in "login.php" , i have seen file "secure.js" And i get username === 'admin' && password === 'strongPassword098765' =>login successful
=>get Flag

![image](https://user-images.githubusercontent.com/95273832/181788536-9a366dcc-f199-4b13-957e-38824aca2610.png)

Flag:picoCTF{j5_15_7r4n5p4r3n7_b0c2c9cb}

4)Search source

![image](https://user-images.githubusercontent.com/95273832/181788647-4a76e30b-9ae1-4d21-8e86-19a5c0ebe148.png)

Solution Now since the name of the question is search source then it pretty much directs us towards its source code. The source code in itself doesn’t have the flag but its files could surely do. But the problem is that we have several files to search which could be tiring and time consuming. A better approach is to give in to laziness and let the process be automated. For this we’ll make a copy of the entire website with the help of a tool called httrack as shown below.

![image](https://user-images.githubusercontent.com/95273832/181788676-8429050c-4c50-4384-8e41-4e315d950512.png)

The next step is to search every file for the flag for which we’ll use grep in a recursive manner. As we already know that the flag begins with pico we’ll leverage that and find the entire flag with the following command: grep -r picoCTF{

![image](https://user-images.githubusercontent.com/95273832/181788717-80962b89-39f7-45d4-9d90-7da7f6d9ee8c.png)

Flag: picoCTF{1nsp3ti0n_0f_w3bpag3s_587d12b8}

5)Forbiddens path

![image](https://user-images.githubusercontent.com/95273832/181788758-570b06c8-4a76-4409-9b77-b280078d411b.png)

Solution This website has the useful feature of reading any file we want it too, given its path. With file paths, a preceeding ./ means the current directory, and ../ means the enclosing directory. Since we know that we are in /usr/share/nginx/html/, and want to access /flag.txt, we can just use the path ../../../../flag.txt to read the flag.

Flag:picoCTF{7h3_p47h_70_5ucc355_26b22ab3}

6)Power Cookie

![image](https://user-images.githubusercontent.com/95273832/181788805-073ce3bc-0772-48eb-b20c-bc5461528273.png)

Solution I used Cookie-editor in google chorme and edit cookie = 1 ,after reload website 
=>get Flag

![image](https://user-images.githubusercontent.com/95273832/181788889-dbb02da4-1825-4470-bcb9-9831de94dedb.png)

Flag:picoCTF{gr4d3_A_c00k13_0d351e23}

7)Roboto Sans

![image](https://user-images.githubusercontent.com/95273832/181788936-e4c10543-9f0b-4542-b03d-e0e3242b0fe8.png)

Solution We are provided with a link to a webpage which doesn’t hold any useful information about the flag. However we do have a hint in the form of the question’s name. Lets see what the robot file has in store for us. We’ll add robots.txt after the URL of the website to visit it. =>I received 1 code,From experience I realize it's base64 encoding decode it and get a plaintext,looks like path of URL.EXACTLY

![image](https://user-images.githubusercontent.com/95273832/181788986-30c5f81b-a15a-4ff5-bd62-da3594ada27f.png)

Flag:picoCTF{Who_D03sN7_L1k5_90B0T5_032f1c2b}

8)Secrets

![image](https://user-images.githubusercontent.com/95273832/181789015-a228a165-f776-449a-bfef-729893a1893f.png)

Solution When i read source code of website.i found folder "secret"

![image](https://user-images.githubusercontent.com/95273832/181789076-ab3c4639-39cf-46be-8262-46d07cba43c1.png)

after go to folder "secret".i continuous folder "hidden"

![image](https://user-images.githubusercontent.com/95273832/181789120-92e79cc4-0dac-466b-921e-1bd536f01bd0.png)

and coninue is folder superhidden =>get Flag

![image](https://user-images.githubusercontent.com/95273832/181789167-2c079e1d-0666-47d9-956a-1017a3b1d180.png)

Flag:picoCTF{succ3ss_@h3n1c@10n_790d2615}

9)SQL Derect

![image](https://user-images.githubusercontent.com/95273832/181789207-a9038d58-5014-469e-9193-676033b3cc18.png)

Solution I run /dt to list the tables of the public scheme and i see a table flags After i did 'select *' to take all data in table flags. Well done

![image](https://user-images.githubusercontent.com/95273832/181789308-dfef2ebf-db23-45cc-b802-6c0c791de1b3.png)

Flag:picoCTF{L3arN_S0m3_5qL_t0d4Y_21c94904}

10)SQLiLite

![image](https://user-images.githubusercontent.com/95273832/181789350-f55af602-261b-4340-bbeb-e616d99f538c.png)D

Solution I tried login using admin:admin and get following web page

![image](https://user-images.githubusercontent.com/95273832/181789384-a7467fd9-18c9-418c-8735-a1bf48825d83.png)

I use SQL injection ' OR 1=1-- as a password, By using this SQL injection to check.

![image](https://user-images.githubusercontent.com/95273832/181789421-29b06081-54a1-4fa8-a05c-d758b85aa5d7.png)

Oh flag in source code

Flag:picoCTF{L00k5_l1k3_y0u_solv3d_it_ec8a64c7}
