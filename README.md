node-random-org-twister
=======================

seeds a twister random number generator from random.org as often as random.org will allow

usage: 

var random = require('./random.js');
console.log(random.random());

enable DEBUG in random.js (this.DEBUG = 1 in RandomOrg constructor) to see the 
data received from random.org.

The default timeout between queries to random.org is calculated in RandomOrg 
constructor and is set to about 144 minutes as the daily free quota is 200000
bits and we request about 20000 bits per query.
Before each request is made, the current quota is checked and no request will
be performed if there are no free bits.

More information about quota: http://www.random.org/clients/http/#quota

No error will be fired if no data from random.org was received; 
it will just continue operation with existing data.
