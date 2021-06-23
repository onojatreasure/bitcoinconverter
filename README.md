# bitcoinconverter

Prerequisites
JDK11 and Maven3 are required for this project

All provided sample code and instructions have been tested with the following versions:

JDK11 and Maven3

Bitcoin Converter Library
This project builds a Java library which contains the following 2 public methods:

`public double getExchangeRate(Currency currency)`

returns in realtime the current Bitcoin exchange rate for the given currency (USD, GBP, or EUR)

`public double convertBitcoins(Currency currency, double coins) throws IllegalArgumentException`

returns the dollar value for the given currency (USD, GBP, or EUR), and the number of Bitcoins

To build the Bitcoin Converter Library perform the following commands:

`mvn clean compile test package`


How To Consume The Library
1. Download the release file and save it. By default it will be saved in yor downloads folder with filename 'bitcoin-converter-svc-lib-1.1.1.jar'
2. Copy the file into the library folder in your local project directory
Example: In your terminal, type the following code
cp ~/Downloads/bitcoin-converter-svc-lib-1.1.1.jar ~/java-bitcoinconverter/client/libs/
3. Install the jar file using maven

```#install bitcoin lib
FILE=`ls libs/`
VERSION=`echo $FILE | egrep -o "([0-9]{1,}\.)+[0-9]{1,}-\w*"`
mvn install:install-file \
 -Dfile=./libs/$FILE \
 -DgroupId=com.cloudacademy \
 -DartifactId=bitcoin-converter-svc-lib \
 -Dversion=$VERSION \
 -Dpackaging=jar 
 
 
 #build and package console app
mvn clean package
