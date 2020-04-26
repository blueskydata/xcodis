# xcodis

[![Build Status](https://travis-ci.org/ledisdb/xcodis.svg?branch=develop)](https://travis-ci.org/siddontang/xcodis) 

[![codecov](https://codecov.io/gh/ledisdb/xcodis/branch/master/graph/badge.svg)](https://codecov.io/gh/ledisdb/xcodis)

Yet another redis proxy based on [codis](https://github.com/wandoulabs/codis)

**Please read codis document first. [here](https://github.com/wandoulabs/codis/blob/master/doc)*

## Install 

+ `git clone github.com/siddontang/xcodis`
+ `make build`

## Why xcodis?

+ Supports [LedisDB](https://github.com/ledisdb/ledisdb).
+ Supports origin Redis, codis uses a modified version.

## Changes from codis

+ Uses db index to represent slot concept in codis.
+ Uses server + db as the connection pool key.
+ `slot_num` in config must equal redis/ledisdb databases. 16 is the default for redis and ledisdb, if you want to use larger one, you must first change redis/ledisdb databases in config. 
+ Uses `scan` + `migrate` in redis for slot migration.
+ Uses `xmigrate` + `xmigratedb` in ledisdb for slot migration.
+ Removes dashboard. 
+ Removes slot rebalance feature.
+ Must set a broker in `config.ini`, broker is `ledisdb` or `redis`.
+ Uses a white command list for ledisdb.
+ Not support atomic tag migration.
+ Not support lua for ledisdb.

## Todo

+ Tidy up some ugly codes I added. >_<

## Thanks

Thanks Wandoujia, codis is a very awesome application.

## Feedback

+ gmail: siddontang@gmail.com
