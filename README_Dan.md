# Documentation of Dan's contribution into FleSe project

## Possibility of sharing (or not sharing) a file

Before this update, each file imported into FleSe was shared with
everyone else. I added the possibility for the user to change that,
using User Options. 

Every file has a Java sharing attribute. This attribute is updated via
an Javascript Ajax request.

## Median algorithm for fuzzifications

The fuzzications values of a new user is calculated following a median
function applied on the existing personalized values of the
app. Contents in Fuzzification algorithms.

## Preventing the owner of the file to modify the fuzzifications of a personalized file

So that the personalization of the users is one of the main axis of
FleSe. Impossible modification if one user personalized it but still
the owner can see all personalization.

## Configuration properties file `config.properties`

The file contains the following variables that can change from one machine to another:

 - Paths of `programFiles`
 - Paths of `plserver`

The file contains 2 or more locations for plserver so it will test the
first one, and if fails takes the second one and etc. So it is
possible to enter the more probable locations into the configuration
file to cover up a maximum range of configuration.

