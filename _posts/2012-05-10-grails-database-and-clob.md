---
title: Grails Database and Clob
author: chris
layout: post
permalink: /2012/05/10/grails-database-and-clob/
dsq_thread_id:
  - 2878563800
categories:
  - Grails
tags:
  - clob
  - database
  - grails
  - groovy
---
Today I came across an interesting defect in my work project. One section of the Grails application allows a user to enter notes e.g. 1000 characters this sounds like nothing just a simple String that is pushed to the controller however we need to store this correctly and the current method was to store the field in the database as a Clob object(Character Large Object). This can store up to 2GB of data as a String, the issue was that this area has never been fully tested.  We then found that durring testing the feild could handle the 1000 characters however if these characters were mixed with return characters (rn) then the Grails application would fail to save the object with the most informative error message &#8220;value refused&#8221;. At first I through that the Clob in the database could not handle return characters but after some testing with smaller strings with a number of return characters this proved wrong.

After some investigation on the net i sound found that there was some issues when mixing Grails, Hibernation and Clob database objects, The first thing that start to ring alarm bells was that the Grail domain object contained a String object that was being used to hold the Clob database value this needed changed. The next issue was trying to sync the Clob object and the existing domain object. Even know storing the Clob as a String and sending the String to Clob was working until now it seemed to fail in the one case, which probably would be picked up by testers. I then took on the task of changing the relation between the domain object and the database table, fist by setting the notes to type Clob, then i hit the first hudle as printing an object type of Clob results in showing a database reference value.  So i then had to create code that would take the notes variable and display it as a String on the web page.  This was achived using the following code:

`<br />
public static String convertClobToString(Clob value) {<br />
        if (value) {<br />
            InputStream stream = value?.getAsciiStream()<br />
            return StringUtil.convertStreamToString(stream)<br />
        } else {<br />
            return ''<br />
        }<br />
    }<br />
`  
`<br />
public static String convertStreamToString(InputStream is) throws Exception {<br />
        BufferedReader reader = new BufferedReader(new InputStreamReader(is))<br />
        StringBuilder sb = new StringBuilder()<br />
        String line = null<br />
        while ((line = reader.readLine()) != null) {<br />
        sb.append(line + "n")<br />
        }<br />
        is.close()<br />
        return sb.toString();<br />
    }<br />
`

This processes the Clob into an input stream then into a String, this function can be placed on the GSP page to print out the value of the notes field in the database. Then for pushing a String into the databse as a Clob is as simple as:

`org.hibernate.Hibernate.createClob(notes);`

&nbsp;

&nbsp;

&nbsp;