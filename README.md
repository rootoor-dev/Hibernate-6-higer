# Hibernate-6-higer
Java Hibernate 6 or higher versions configurations' files

## via fichier "hibernate.properties"

```java

hibernate.connection.driver_class = org.postgresql.Driver
hibernate.connection.url = jdbc:postgresql://localhost/mydatabase
hibernate.connection.username = myuser
hibernate.connection.password = secret
hibernate.c3p0.min_size=5
hibernate.c3p0.max_size=20
hibernate.c3p0.timeout=1800
hibernate.c3p0.max_statements=50
hibernate.dialect = org.hibernate.dialect.PostgreSQLDialect
```

## via fichier "hibernate.cfg.xml"

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE hibernate-configuration PUBLIC 
  "-//Hibernate/Hibernate Configuration DTD 3.0//EN" 
  "http://www.hibernate.org/dtd/hibernate-configuration-3.0.dtd">
<!-- Version 8 MySQL hiberante-cfg.xml example for Hibernate 5 -->
<hibernate-configuration>
  <session-factory>
    <property name="connection.driver_class">com.mysql.cj.jdbc.Driver</property>
    <!-- property name="connection.driver_class">com.mysql.jdbc.Driver</property -->
    <property name="connection.url">jdbc:mysql://localhost/database</property>
    <property name="dialect">org.hibernate.dialect.MySQL8Dialect</property>
    <property name="connection.username">root</property>
    <property name="connection.password">password</property>
    <property name="connection.pool_size">3</property>
    <!--property name="dialect">org.hibernate.dialect.MySQLDialect</property-->
    <property name="current_session_context_class">thread</property>
    <property name="show_sql">true</property>
    <property name="format_sql">true</property>
    <property name="hbm2ddl.auto">update</property>
    <!-- mapping class="com.mcnz.jpa.examples.Player" / -->
  </session-factory>
</hibernate-configuration>
```

## JPA persistence.xml

```XML
<persistence xmlns="http://xmlns.jcp.org/xml/ns/persistence"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" version="2.2"
    xsi:schemaLocation="http://xmlns.jcp.org/xml/ns/persistence http://xmlns.jcp.org/xml/ns/persistence/persistence_2_2.xsd">
    <persistence-unit name="jpa-examples">
        <description>Sample PostgresQL persistence.xml file</description>
        <provider>org.hibernate.jpa.HibernatePersistenceProvider</provider>
        <exclude-unlisted-classes>false</exclude-unlisted-classes>
        <properties>
            <!-- JDBC connection properties -->
            <property name="javax.persistence.jdbc.driver" value="org.postgresql.Driver" />
            <property name="javax.persistence.jdbc.url" value="jdbc:postgresql://127.0.0.1:5432/jpa_db" />
            <property name="javax.persistence.jdbc.user" value="root" />
            <property name="javax.persistence.jdbc.password" value="password" />
            <!-- custom Hibernate property -->
            <property name="hibernate.dialect" value="org.hibernate.dialect.PostgreSQL95Dialect"/>
			<!-- database creation settings -->
			<property name="javax.persistence.schema-generation.database.action" value="create" />
			<property name="javax.persistence.sql-load-script-source" value="table-records.sql" />
			<!-- JPA selective caching enabled -->
			<shared-cache-mode>ENABLE_SELECTIVE</shared-cache-mode>
        </properties>
    </persistence-unit>
</persistence>


<persistence version="2.2" 
   xmlns="http://xmlns.jcp.org/xml/ns/persistence"  
   xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
   xsi:schemaLocation="http://xmlns.jcp.org/xml/ns/persistence   
    http://xmlns.jcp.org/xml/ns/persistence/persistence_2_2.xsd"
  >
    <persistence-unit name="jpa-example">
	<!--persistence-unit name="jpa-tutorial"-->
	
		<class>com.mcnz.jpa.examples.Player</class>
		
		<!--
		<jar-file>hibernate-and-jpa-entities.jar</jar-file>
		<exclude-unlisted-classes>true</exclude-unlisted-classes>
		-->  

		<properties>
	        <!--property name="javax.persistence.jdbc.driver" value="com.mysql.jdbc.Driver"/-->
			<property name="javax.persistence.jdbc.driver" value="com.mysql.cj.jdbc.Driver"/>
            <property name="javax.persistence.jdbc.url" value="jdbc:mysql://localhost/jpa_database"/> 
            <property name="hibernate.dialect" value="org.hibernate.dialect.MySQL8Dialect" />
            <property name="javax.persistence.jdbc.user" value="root"/> 
            <property name="javax.persistence.jdbc.password" value="password"/>
            <property name="hibernate.show_sql" value = "true" /> 
            <property name="hibernate.format_sql" value = "true" />
			
            <property name="javax.persistence.schema-generation.database.action" value="drop-and-create"/> 
			<!--
			<property name="javax.persistence.query.timeout" value="99"/>
			<property name="javax.persistence.lock.timeout" value="99"/> 
			<shared-cache-mode>ALL</shared-cache-mode>
			
			<property name="javax.persistence.schema-generation.database.action" value="drop-and-create" />
			<property name="javax.persistence.sql-load-script-source" value="table-records.sql" />
			-->
	    </properties>
	       
	</persistence-unit> 
	 
</persistence>


<persistence version="2.2" 
   xmlns="http://xmlns.jcp.org/xml/ns/persistence"  
   xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
   xsi:schemaLocation="http://xmlns.jcp.org/xml/ns/persistence   
    http://xmlns.jcp.org/xml/ns/persistence/persistence_2_2.xsd"
  >
    <persistence-unit name="jpa-example">
	<!--persistence-unit name="jpa-tutorial"-->
	
		<class>com.mcnz.jpa.examples.Player</class>
		
		<!--
		<jar-file>hibernate-and-jpa-entities.jar</jar-file>
		<exclude-unlisted-classes>true</exclude-unlisted-classes>
		-->  

		<properties>
	        <!--property name="javax.persistence.jdbc.driver" value="com.mysql.jdbc.Driver"/-->
			<property name="javax.persistence.jdbc.driver" value="com.mysql.cj.jdbc.Driver"/>
            <property name="javax.persistence.jdbc.url" value="jdbc:mysql://localhost/hibernate_examples"/> 
            <property name="hibernate.dialect" value="org.hibernate.dialect.MySQL8Dialect" />
            <property name="javax.persistence.jdbc.user" value="root"/> 
            <property name="javax.persistence.jdbc.password" value="password"/>
            <property name="hibernate.show_sql" value = "true" /> 
            <property name="hibernate.format_sql" value = "true" />
			
            <property name="javax.persistence.schema-generation.database.action" value="drop-and-create"/> 
			<!--
			<property name="javax.persistence.query.timeout" value="99"/>
			<property name="javax.persistence.lock.timeout" value="99"/> 
			<shared-cache-mode>ALL</shared-cache-mode>
			
			<property name="javax.persistence.schema-generation.database.action" value="drop-and-create" />
			<property name="javax.persistence.sql-load-script-source" value="table-records.sql" />
			-->
	    </properties>
	       
	</persistence-unit> 
	 
</persistence>

```


