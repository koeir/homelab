# No Packets Coming In

## ISSUE

> Packets are going out, but no packets seem to be coming in.
> Client successfully connects, but packet loss iss 100% when pinging.
> Behavior is consistent over different networks.

## CAUSE

> The `tun0` interface is not being initialized properly, starting as `DOWN`

## FIX/SOLUTION

> No clue as for the actual cause, likely race conditions, but I'm not good enough to figure out an actual fix.
> Instead, I made a oneshot script that checks the `tun0` status when it is initialized, activating it if it starts as `DOWN`.
