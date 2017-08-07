# Data-Sending-to-UF-to-UF
Forwarding Data From on Universal Forwarder to Another Universal Forwarder

Simply configure a tcpout stanza in the outputs.conf of the first Forwarder to forward to Intermediary Forwarder:

 [tcpout]
 defaultGroup=intermediaryForwarder
 
 [intermediaryForwarder]
 server=myintermediaryforwarder.company.com:9997
Then, configure a splunktcp stanza in the inputs.conf of the Intermediary Forwarder:

 [splunktcp://:9997]
...as well as a another tcpout in the Intermediary Forwarder to forward to Indexers:

 [tcpout]
 defaultGroup=indexers
 
 [indexers]
 server=myindexer:9997
