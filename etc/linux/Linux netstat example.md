# Linux netstat example
`netstat` command is used to see the network connections. 

Show how many tcp connections are on the current machine.
```
netstat -natp
```

Commonly used parameters
```
   -a, --all
       Show both listening and non-listening (for TCP this means established connections) sockets.  With
       the --interfaces option, show interfaces that are not marked

   --numeric , -n
       Show numerical addresses instead of trying to determine symbolic host, port or user names.
       
   --tpc, -t
       Show tcp connections
       
   -p, --program
       Show the PID and name of the program to which each socket belongs.    
```

The output content is probably like this
```
tcp        0      0 10.145.134.204:8668         10.145.48.13:35178          TIME_WAIT   -                   
tcp        0      0 10.145.134.204:8668         10.145.117.74:36580         TIME_WAIT   -                   
tcp        0      0 10.145.134.204:8668         10.145.117.74:36862         TIME_WAIT   -                   
tcp        0      0 10.145.134.204:8668         10.145.70.134:34556         TIME_WAIT   -                   
tcp        0      0 10.145.134.204:8668         10.145.198.133:44976        TIME_WAIT   -                   
tcp        0      0 10.145.134.204:8668         10.145.159.10:40304         TIME_WAIT   -                   
tcp        0      0 10.145.134.204:8668         10.145.86.4:60560           TIME_WAIT   -                   
tcp        0      0 10.145.134.204:40244        10.145.181.202:8988         ESTABLISHED 146/java            
tcp        0      0 10.145.134.204:51784        10.145.170.136:8988         ESTABLISHED 146/java    
```

Detailed explanation of the output
```
OUTPUT
   Active Internet connections (TCP, UDP, raw)
   Proto
       The protocol (tcp, udp, raw) used by the socket.

   Recv-Q
       The count of bytes not copied by the user program connected to this socket.

   Send-Q
       The count of bytes not acknowledged by the remote host.

   Local Address
       Address  and  port  number  of  the local end of the socket.  Unless the --numeric (-n) option is
       specified, the socket address is resolved to its canonical host name (FQDN), and the port  number
       is translated into the corresponding service name.

   Foreign Address
       Address and port number of the remote end of the socket.  Analogous to "Local Address."

   State
       The state of the socket. Since there are no states in raw mode and usually no states used in UDP,
       this column may be left blank. Normally this can be one of several values:
       ESTABLISHED
              The socket has an established connection.

       SYN_SENT
              The socket is actively attempting to establish a connection.

       SYN_RECV
              A connection request has been received from the network.

       FIN_WAIT1
              The socket is closed, and the connection is shutting down.

       FIN_WAIT2
              Connection is closed, and the socket is waiting for a shutdown from the remote end.

       TIME_WAIT
              The socket is waiting after close to handle packets still in the network.

       CLOSED The socket is not being used.

       CLOSE_WAIT
              The remote end has shut down, waiting for the socket to close.

       LAST_ACK
              The remote end has shut down, and the socket is closed. Waiting for acknowledgement.

       LISTEN The socket is listening for incoming connections.  Such sockets are not  included  in  the
              output unless you specify the --listening (-l) or --all (-a) option.

       CLOSING
              Both sockets are shut down but we still don’t have all our data sent.

       UNKNOWN
              The state of the socket is unknown.
```

EOF

