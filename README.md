# WHISPER 1.0

**WHISPER**, or **Wisconsin-HPL Suite for Persistence** is a comprehensive benchmark
suite for emerging persistent memory technologies. For more details :

**An Analysis of Persistent Memory Use with WHISPER**. *ASPLOS'17*.

Sanketh Nalli, Swapnil Haria, Mike Swift, Mark Hill, Haris Volos, Kim Keeton.


## IMPORTANT
We are currently testing WHISPER in various environments.
PLEASE USE AT YOUR OWN RISK.
Report issues and suggestions to Swapnil (swapnilh at cs dot wisc edu) or Sanketh (sankey
at cs dot wisc dot edu). 

## To download: 
~~~
   	$ git clone https://github.com/swapnilh/whisper.git
	$ cd whisper
	$ git submodule update --init
~~~

## To build:
~~~
	$ cd whisper
	$ ./script.py -b -w	{ycsb,tpcc,echo,redis,ctree,hashmap,memcached,vacation,nfs,exim,sql,all}
~~~

## To run (tracing is optional, but need to be root for it):
~~~
	$ cd whisper
	$ ./script.py -c [-t] -z {l|xl|xxl} -w  {ycsb,tpcc,echo,redis,ctree,hashmap,memcached,vacation,nfs,exim,sql,all}
~~~

## To clean:
~~~
	$ cd whisper
	$ ./script.py -c -w {ycsb,tpcc,echo,redis,ctree,hashmap,memcached,vacation,nfs,exim,sql,all}
~~~

## To update:
~~~
	$ cd whisper
	$ ./script -u
	git submodule update --remote
	git submodule update status

~~~

## For help:
~~~
	$ cd whisper
	$ ./script -h

usage: script [-h] [-b] [-r] -w
              {ycsb,tpcc,echo,redis,ctree,hashmap,memcached,vacation,nfs,exim,sql,all}
              [-z {l,xl,xxl}] [-t] [-c] [-u]
              [-p {ycsb,tpcc,echo,redis,ctree,hashmap,memcached,vacation,nfs,exim,sql,all}]

Buildi, Clean, Run, Update WHISPER

optional arguments:
  -h, --help            show this help message and exit
  -b                    Build workload
  -r                    Run workload
  -w {ycsb,tpcc,echo,redis,ctree,hashmap,memcached,vacation,nfs,exim,sql,all}
                        Workload
  -z {l,xl,xxl}         Set workload size
  -t                    Enable tracing. Need to be root.
  -c                    Clean workload
  -u                    Update benchmark
  -p {ycsb,tpcc,echo,redis,ctree,hashmap,memcached,vacation,nfs,exim,sql,all}
                        More help with a workload

~~~

## For more help:
~~~
Example,
	$ ./script -w vacation -p 

Usage: ./build/bench/stamp-kozy/vacation/vacation [options]

Options:                                             (defaults)
    c <UINT>   Number of [c]lients                   (1)
    n <UINT>   [n]umber of user queries/transaction  (10)
    q <UINT>   Percentage of relations [q]ueried     (90)
    t <UINT>   Number of [t]ransactions              (131072)
    r <UINT>   Number of [r]ows		       (5767168)
    u <UINT>   Percentage of [u]ser transactions     (80)
    e <UINT>   Enable trac[e] collection             (0)

~~~
