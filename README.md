1. Выбрать место размещения *.v8i файлов (файл настройки подключения и запуска базы)
2. В папке: %systemdrive%\ProgramData\1C\1CEStart найти файл "1cestart.cfg" и добавить туда запис\си вида:
```
CommonInfoBases=%путь_к_файлу%\%имя файла%.v8i
```
3. В файле "%имя файла%.v8i" прописываем параметры базы, пример:
 ```
	[base id_1]
	Connect=Srvr="server-1:1541";Ref="base_id_1";
	Folder=/Dev
	ClientConnectionSpeed=Normal
	App=ThinClient
	WA=1
	Version=8.3
	AdditionalParameters=/ClearCache /TComp -None /O Normal /iTaxi /SLev0 /L ru /VL ru /RunModeManagedApplication /DisableStartupMessages /UseHwLicenses- /AppAutoCheckVersion-
	AppArch=x86_64
```

Содержимое первой строки, в примере это "[base id_1]", должно быть уникально в пределах корня\папки списка баз, иначе будет отображена только 1на, последняя в списке база

4. При запуске ярлыка 1С, она автоматически считывает каждый раз содержимое файла "1cestart.cfg" и показывает список баз
5. На файлы "%имя файла%.v8i" через GP можно повесить права доступа и пользователь увидит только те базы, к котоым у него есть доступ.
6. Файл "Delete 1C temp and work folder.xml" - чистит у всех пользователь папки 1С и заливает подготовленный шаблок окна запуска 1С (показывать базы в виде дерева)
