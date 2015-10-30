# sample

```
$ git clone https://github.com/mururu/sample_for_cluster_info.git sample1
$ git clone https://github.com/mururu/sample_for_cluster_info.git sample2
```

in shell A (OTP 18)

```
$ cd sample1
$ ./rebar3 release
$ ./_build/default/rel/sample/bin/sample console
```

in shell B (OTP 17)

```
$ cd sample2
$ vim config/vm.args
# change name from sample1@127.0.0.1 to sample2@127.0.0.1
$ ./rebar3 release
$ ./_build/default/rel/sample/bin/sample console
> net_kernel:connect_node('sample1@127.0.0.1').
> cluster_info:dump_all_connected("/tmp/report.all-nodes.html").
```
