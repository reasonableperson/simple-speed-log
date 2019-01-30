# simple-speed-log

Two shell scripts which can be run on any device with Python and
[Miller][1]. You'll need to install [speedtest-cli][2] from `pip`.

`./monitor` is a shell script that calls `speedtest` and waits a random
number of seconds, up to one hour, before doing the next test.  It can be
run in `screen` on embedded platforms where `cron` may not be available or
reliable. Each test is logged to `speed.log` in CSV format.

`./view` is a shell script that calls `mlr` and dumps the most interesting
parts of `speed.log` in a nice format.

```
λ ./view
+-------------+----------+------------+-----------+
| Date        | Time     | Download   | Upload    |
+-------------+----------+------------+-----------+
| 30 Jan 2019 | 21:00 pm | 85.19 Mbps | 0.31 Mbps |
| 30 Jan 2019 | 21:17 pm | 85.74 Mbps | 0.29 Mbps |
| 30 Jan 2019 | 21:34 pm | 85.06 Mbps | 0.26 Mbps |
+-------------+----------+------------+-----------+
```

[1]: https://github.com/johnkerl/miller
[2]: https://github.com/sivel/speedtest-cli
