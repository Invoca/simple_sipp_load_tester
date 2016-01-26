# Load Tester

Here is how you run a load test

    $./sipp -sf simple.xml -s #PROMO_NUMBER# #RINGSWITCH_NUMBER# -i #YOUR_IP# -r #RATE# -m #MAX_CALLS# -trace_err -trace_shortmsg -trace_stat
    
This command makes reference to the included binary compiled against:

    $ uname -a
    Darwin nbjcook.local 15.0.0 Darwin Kernel Version 15.0.0: Sat Sep 19 15:53:46 PDT 2015; root:xnu-3247.10.11~1/RELEASE_X86_64 x86_64
    
The following parameters must be included:

- `#PROMO_NUMBER#` - the number being called
- `#RINGSWITCH_NUMBER#` - the IP associated with the SIP server being called
- `#YOUR_IP#` - the IP of the local machine running this test
- `#RATE#` - how many calls that will be launched each minute
- `#MAX_CALLS` the total number of calls in the test

## Getting your local ip

Run this:

    $ ifconfig | grep en0 -A 5 | grep 'inet '
