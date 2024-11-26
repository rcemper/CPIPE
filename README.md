# CPIPE
The example shows how to run a server command from within Caché / Ensemble / IRIS 
and get back the full output as seen in any server command shell. 
Instead of just displaying the result the more useful purpose is to check the interesting lines 
and just skip the rest. 
It's definitely easier than $ZF(-1,..) and $ZF(-2,...) exercises. 

#### Demo1 ###
~~~
   IRISAPP>d cmd^Zpipe("ping community.intersystems.com")
 
Ping wird ausgeführt für community.intersystems.com [54.83.203.138] mit 32 Bytes Daten:
Antwort von 54.83.203.138: Bytes=32 Zeit=120ms TTL=47
Antwort von 54.83.203.138: Bytes=32 Zeit=120ms TTL=47
Antwort von 54.83.203.138: Bytes=32 Zeit=119ms TTL=47
Antwort von 54.83.203.138: Bytes=32 Zeit=119ms TTL=47
 
Ping-Statistik für 54.83.203.138:
    Pakete: Gesendet = 4, Empfangen = 4, Verloren = 0
    (0% Verlust),
Ca. Zeitangaben in Millisek.:
    Minimum = 119ms, Maximum = 120ms, Mittelwert = 119ms
~~~
#### hint ####
You may add this line to %ZLANGC00.mac to make usage easier
~~~
   ZPIPE(%a) do cmd^Zpipe(%a) quit
~~~
#### Demo2 ####
~~~
   IRISAPP>zpipe "ping community.intersystems.com"
 
Ping wird ausgeführt für community.intersystems.com [54.83.203.138] mit 32 Bytes Daten:
Antwort von 54.83.203.138: Bytes=32 Zeit=123ms TTL=47
Antwort von 54.83.203.138: Bytes=32 Zeit=119ms TTL=47
Antwort von 54.83.203.138: Bytes=32 Zeit=239ms TTL=47
Antwort von 54.83.203.138: Bytes=32 Zeit=119ms TTL=47
 
Ping-Statistik für 54.83.203.138:
    Pakete: Gesendet = 4, Empfangen = 4, Verloren = 0
    (0% Verlust),
Ca. Zeitangaben in Millisek.:
    Minimum = 119ms, Maximum = 239ms, Mittelwert = 150ms
 
IRISAPP>
~~~

[Article in DC](https://community.intersystems.com/post/execute-server-commands-cach%C3%A9-ensemble-iris)     
     
