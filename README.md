# Load Tester

This repo consists of:

1. a binary compiled for the system kernel listed below
1. an xml scenario that should be modified with extreme caution
1. this README

This command makes reference to the included binary compiled against:

    $ uname -a
    Darwin nbjcook.local 15.0.0 Darwin Kernel Version 15.0.0: Sat Sep 19 15:53:46 PDT 2015; root:xnu-3247.10.11~1/RELEASE_X86_64 x86_64

## Running a Test

Here is how you run a load test

    $./sipp -sf simple.xml -s #PROMO_NUMBER# #RINGSWITCH_NUMBER# -i #YOUR_IP# -r #RATE# -m #MAX_CALLS# -trace_err -trace_shortmsg -trace_stat
    
The following parameters must be included:

- `#PROMO_NUMBER#` - the number being called
- `#RINGSWITCH_NUMBER#` - the IP associated with the SIP server being called
- `#YOUR_IP#` - the IP of the local machine running this test
- `#RATE#` - how many calls that will be launched each minute
- `#MAX_CALLS` - the total number of calls in the test

For example, to call the number 888-555-1212 at the IP 55.55.55.55 from the local IP 10.0.0.1 ten times initiating one call per second, use

    $./sipp -sf simple.xml -s 888-555-1212 55.55.55.55 -i 10.0.0.1 -r 1 -m 10 -trace_err -trace_shortmsg -trace_stat


## Getting your local ip

Run this:

    $ ifconfig | grep en0 -A 5 | grep 'inet ' | cut -d ' ' -f 2
