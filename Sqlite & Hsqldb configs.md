# Les Bases de donnees memoire

--Une base de données `mem:` est spécifiée par le protocole` mem:`.
 Pour de telles BD, le chemin est simplement un nom. Sans extension (.db, .hsql, .hsqldb). Plusieurs bases de données `mem:` peuvent exister en même temps et se distinguer par leurs noms.
 Dans l'exemple ci-dessous, la base de données s'appelle "mymemdb".
 Exemple : jdbc:hsqldb:mem:mymemdb

--Une base de données `file:` est spécifiée par le protocole` file:`.
 Pour de telles BD, le chemin est un chemin dont le fichier est sans extension (.db, .hsql, .hsqldb). Plusieurs bases de données `file:` peuvent exister en même temps et se distinguer par leurs noms. Lors de l'utilisation de chemins relatifs, ces chemins seront pris par rapport au répertoire dans lequel la commande shell pour démarrer la machine virtuelle Java a été exécutée.
 Dans l'exemple ci-dessous, la base de données s'appelle "testdb".
 Exemple : jdbc:hsqldb:file:/opt/db/testdb

--Une base de données `res:` est spécifiée par le protocole `res:`. Comme il s'agit d'une ressource Java, le chemin de la base de données est une URL Java (similaire au chemin d'accès à une classe). Dans l'exemple ci-dessous, `"resdb"` est le nom racine des fichiers de la base de données, qui existe dans le répertoire `"org/my/path"` dans le classpath (probablement dans un Jar). **Une ressource Java est stockée dans un format compressé et est décompressée en mémoire lorsqu'elle est utilisée**. Pour cette raison, une base de données `res:` ne doit pas contenir de grandes quantités de données et est toujours en lecture seule.
 Dans l'exemple ci-dessous, la base de données s'appelle "resdb".
 Exemple : jdbc:hsqldb:res:org.my.path.resdb

-- Une base de données sur Serveur :
 via URL http : jdbc:hsqldb:hsql://localhost/testdb
 via URL https : jdbc:hsqldb:hsqls://localhost/testdb
 via URL https : jdbc:hsqldb:https://localhost/testdb


## Types of catalog data (Accès in-process aux catalogues de base de données)

`mem`: stored entirely in RAM - without any persistence beyond the JVM process's life

`file`: stored in file system

`res`: stored in a Java resource, such as a Jar and always read-only

```
SQLite

-- File 
jdbc:hsqldb:file:/Chemin/vers/testdb
jdbc:sqlite:C:\sqlite3.38.5\bin\db\chinook.db
jdbc:sqlite:C:/sqlite3.38.5/bin/db/chinook.db

-- mem 
jdbc:hsqldb:mem:nomBaseDonnees
jdbc:hsqldb:mem:test

-- res
jdbc:hsqldb:res:packqge.vers.le.fichier.nomBaseDonnees
jdbc:hsqldb:res:org.my.path.resdb

source : http://www.hsqldb.org/doc/2.0/guide/running-chapt.html

```

SQLite 3

url => jdbc:sqlite:C:\sqlite3.38.5\bin\db\chinook.db
jdbc.driver => org.hsqldb.jdbcDriver
jdbc.url => jdbc:sqlite:C:\sqlite3.38.5\bin\db\chinook.db      --{bd fichier}
jdbc.url => jdbc:hsqldb:mem:test      --{bd memoire}
jdbc.url => jdbc:hsqldb:mem:test      --{bd memoire}
jdbc.url => jdbc:hsqldb:mem:test      --{bd memoire}
jdbc.user => sa
jdbc.password => {laisser vide}
hibernate.dialect => org.hibernate.dialect.HSQLDialect

HSQLDB 

jdbc.driver => org.hsqldb.jdbcDriver
jdbc.url => jdbc:hsqldb:mem:test      --{bd memoire}
jdbc.user => sa
jdbc.password => {laisser vide}
hibernate.dialect => org.hibernate.dialect.HSQLDialect





























