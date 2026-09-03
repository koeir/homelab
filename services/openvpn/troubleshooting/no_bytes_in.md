# No Packets Coming In

## ISSUE
> Packets are going out, but packets seem to be coming in. 
> Client successfully connects, but packet loss iss 100% when pinging. 
> Behavior is consistent over different networks.

## CAUSE
> The `tun0` interface is not being initialized properly, starting as `DOWN`

## FIX/SOLUTION
> Made a oneshot script that checks the `tun0` status when it is initialized, 
> activating it if it starts as `DOWN`.
