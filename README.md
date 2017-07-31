# iOS_envirement_config_demo
this demo show how to manage and config different url for you iOS project's envirement


How to use it:

Steps:
1、duplicate your project in the targets in the Xcode, and rename the duplicated target, remove the copy info.plist of the duplicated target. and choose the origin info.plist as the info.plist for the duplicated target in the General tag.

2、edit your schemes for the targets of your project: delete the schemes which name like <target>copy, and create new schemes from the targets your just created through duplicating the origin target

3、create a folder in your project which named like configs (or any name as you wish!),and create some subfolders(examples name:subfolder1,subfolder2) to save your configure file.

4、create a Category file for NSObject as the configure file (in here we named it NSObject+Catagory), and move or copy the '.m' file of to each subfolder of the 'configs' folder.

5、in the Category file's '.h' file define your configure file use "extern Const NSString * a;" ,just like below:

extern Const NSString *baseURL;

and define the value in the '.m' file of each configure folder. like below:

in the subfolder1 NSObject+Category.m file:
Const NSString *baseURL = @"https://www.example1.com"

in the subfolder2 NSObject+Category.m file:
Const NSString *baseURL = @"https://www.example2.com"

6、finally import the NSObject+Category.h file to the .pch file in your project,and you can access the different value when you choose the different scheme of your project.

you can see the example in the demo.
