JOINS
=======

This appup will be used for joining multiple tables and get records..
The Inner Join selects records that have matching values in both tables.
 
 
Let us take example of where ticket table joining with domain table getting domain name.
The input data has to be sent as part of the request body as JSON format. Any attribute that is not needed for a particular operation should not be included.   

 
**Trigger Expression** : /v1/join/

**Method** : ”POST”

**Content-Type** : application/json

**A sample is given below:**

{"data":{

"fields": "t.id,count(tn.is_reply) as count",

"tables":[
{"ticket_note":"tn"},
{"ticket":"t"}
],

"join":[
{
"join_type":"left join", 
"table1":"tn",
"join_column1":"ticket_id",
"table2":"t",
"join_column2":"id"
}],

"group_by":"t.id"
}

}

**RestCall**: ”POST”: [https://dbapp.500apps.com/v2/joins](https://dbapp.500apps.com/v2/joins)

![Image](Icon-pictures.png "image")
