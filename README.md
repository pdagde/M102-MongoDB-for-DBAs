
WEEK 2:

homework 1:

We will use the pcat.products collection from week 1. So start with that; if not already set up, import it:

mongoimport --drop -d pcat -c products products.json
You can find products.json from the Download Handouts link.

In the shell, go to the pcat database. If you type:

use pcat;
db.products.count()
the shell should return 11.

Next, download homework2.js from the Download Handouts link. Run the shell with this script:

mongo --shell pcat homework2.js
First, make a mini-backup of the collection before we start modifying it. In the shell:

b = db.products_bak; db.products.find().forEach( function(o){ b.insert(o) } )
 // check it worked:
b.count()
// should print 11
If you have any issues you can restore from "products_bak"; or, you can re-import with mongoimport. (You would perhaps need in that situation to empty the collection first or drop it; see the --drop option on mongoimport --help.)

In the shell, type:

homework.a()
What is the output? (The above will check that products_bak is populated.)


#### ANS : 3.05

@@@@@@homework 2@@@@@@@@@@


Add a new product to the products collection of this form:

{
    "_id" : "ac9",
    "name" : "AC9 Phone",
    "brand" : "ACME",
    "type" : "phone",
    "price" : 333,
    "warranty_years" : 0.25,
    "available" : true
}
Note: in general because of the automatic line continuation in the shell, you can cut/paste in the above and shouldn't have to type it all out. Just enclose it in the proper statement(s) to get it added.

Next, load into a shell variable the object corresponding to

_id : ObjectId("507d95d5719dbef170f15c00")
Then change term_years to 3 for that document. (And update it in the database.)
Then change over_rate for sms in limits to 0.01 from 0. Update that too.
At the shell prompt type:

homework.b()
What is the output?





#### ANSWER : 0.050.019031











