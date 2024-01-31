# 幻兽帕鲁存档迁移 Palworld_save_migration
本代码可实现幻兽帕鲁存档的迁移(从linux到linux服务器)
# 请在迁移存档前务必做好备份！！！
步骤如下（以linux服务器之间为例）  
# 第一步，在新服务器上创建一个游戏，生成一个新的存档。  
# 第二步，将新服务器的存档复制到代码文件的target/Saved文件夹下如果没有这个文件夹，自己创建一个文件夹，注意大小写保持一致。 
 例：/home/steam/Steam/steamapps/common/PalServer/Pal/Saved/SaveGames/0/<save_id>/的内容
复制Players文件夹，Level.sav，LevelMeta.sav即可
# 第三步 按顺序将新旧存档写入source.txt和target.txt中每行一个存档名，不含扩展名
例子：fdafdasf 是旧存档下张三的角色文件，asasas是它的新文件。那么在source.txt和target.txt中， fdafdasf和asasas是在同一行的
# 第三步，将老存档（Players文件夹，Level.sav，LevelMeta.sav）复制到代码文件的source/Saved文件夹下  
# 第四步，按照文件顺序依次运行python程序。所有python程序运行完成后，会得到一个final文件夹  
# 第五步，将final文件夹里面的内容复制到新服务器的对应的存档位置中进行替换  
# 注意事项
假设旧服务器上有五人，新服务器上暂时只能三人创建存档，那么完成一次上述操作后，新服务器只会迁移这三个人的存档。第四、第五人迁移时需要完全重来

# 随时更新，如果有什么疑问，还请留言。我会尽力解决


##

**Pal world Save Migration**

These Scripts provide a method to migrate your Pal world save between servers running on different OS’s (i.e Windows to Linux)

Before you start please make sure to create backups of all save files!!!

Step 1: 
- Create a new server and generate a save file.
- each player on the old server will need to login and create a blank/empty character

Step 2:
- Create 2 folder trees in the root of this project, the first folder will be target/Saved and the other one is source/Saved
- Copy the new server’s save files into target/Saved
- Copy the old server’s save files into source/Saved

It should look like this when your done.
```
.
├── target/
│ └── Saved/
│ ├── Players/
│ │ ├── 076459B6000000000000000000000000.sav
│ │ └── ...
│ ├── Level.sav
│ └── LevelMeta.sav
├── source/
│ └── Saved/
│ ├── Players/
│ │ ├── 2cfedae8000000000000000000000000.sav
│ │ └── ...
│ ├── Level.sav
│ └── LevelMeta.sav
├── source.txt
├── target.txt
└── ...
```


Step 3: 
- we will need to map the old players UID to the new players UID
- these will be placed in source.txt and target.txt
- for this example the source user john1 has the UID of 2cfedae8000000000000000000000000 
- the target user john2 has the UID of 076459B6000000000000000000000000

these should be on the same line in the respective text files

source.txt
```
2cfedae8000000000000000000000000
```
target.txt
```
076459B6000000000000000000000000
```

Step 4: 
- Run the Python scripts in the given order. (step1, step2, ...)
- Once all scripts have finished a Final folder will be generated

Note: 
- The time to run these scripts will depend greatly on how large you save is and how many players are being migrated

Step 5: 
- Copy the contents of the final folder to the corresponding save location on the new server


Constantly updated. If you have any questions, please leave a message. I will try my best to solve them.

![image](https://github.com/shuai2955/Palworld_save_migration/blob/main/qqchat.png)
