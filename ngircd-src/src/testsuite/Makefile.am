#
# ngIRCd -- The Next Generation IRC Daemon
# Copyright (c)2001-2014 Alexander Barton (alex@barton.de) and Contributors
#
# This program is free software; you can redistribute it and/or modify
# it under the terms of the GNU General Public License as published by
# the Free Software Foundation; either version 2 of the License, or
# (at your option) any later version.
# Please read the file COPYING, README and AUTHORS for more information.
#

AUTOMAKE_OPTIONS = serial-tests #../portab/ansi2knr (disabled by ./autogen.sh script)

AM_CPPFLAGS = -I$(srcdir)/../portab

EXTRA_DIST = \
	Makefile.ng README functions.inc getpid.sh \
	start-server.sh stop-server.sh tests.sh stress-server.sh \
	test-loop.sh wait-tests.sh \
	channel-test.e connect-test.e check-idle.e invite-test.e \
	join-test.e kick-test.e message-test.e misc-test.e mode-test.e \
	opless-channel-test.e server-link-test.e who-test.e whois-test.e \
	stress-A.e stress-B.e \
	server-login-test.e \
	start-server1 stop-server1 ngircd-test1.conf \
	start-server2 stop-server2 ngircd-test2.conf

all:

clean-local:
	rm -rf logs tests *-test ngircd-test*.log procs.tmp tests-skipped.lst \
	 T-ngircd1 ngircd-test1.motd T-ngircd2 ngircd-test2.motd

maintainer-clean-local:
	rm -f Makefile Makefile.in Makefile.am

check_SCRIPTS = ngircd-TEST-Binary tests.sh

ngircd-TEST-Binary:
	cp ../ngircd/ngircd T-ngircd1
	cp ../ngircd/ngircd T-ngircd2
	[ -f getpid.sh ] || ln -s $(srcdir)/getpid.sh .
	rm -f tests-skipped.lst

connect-test: tests.sh
	rm -f connect-test
	ln -s $(srcdir)/tests.sh connect-test

channel-test: tests.sh
	rm -f channel-test
	ln -s $(srcdir)/tests.sh channel-test

invite-test: tests.sh
	rm -f invite-test
	ln -s $(srcdir)/tests.sh invite-test

join-test: tests.sh
	rm -f join-test
	ln -s $(srcdir)/tests.sh join-test

kick-test: tests.sh
	rm -f kick-test
	ln -s $(srcdir)/tests.sh kick-test

message-test: tests.sh
	rm -f message-test
	ln -s $(srcdir)/tests.sh message-test

misc-test: tests.sh
	rm -f misc-test
	ln -s $(srcdir)/tests.sh misc-test

mode-test: tests.sh
	rm -f mode-test
	ln -s $(srcdir)/tests.sh mode-test

opless-channel-test: tests.sh
	rm -f opless-channel-test
	ln -s $(srcdir)/tests.sh opless-channel-test

server-link-test: tests.sh
	rm -f server-link-test
	ln -s $(srcdir)/tests.sh server-link-test

server-login-test: tests.sh
	rm -f server-login-test
	ln -s $(srcdir)/tests.sh server-login-test

who-test: tests.sh
	rm -f who-test
	ln -s $(srcdir)/tests.sh who-test

whois-test: tests.sh
	rm -f whois-test
	ln -s $(srcdir)/tests.sh whois-test

TESTS = start-server1 \
	connect-test \
	start-server2 \
	channel-test \
	invite-test \
	join-test \
	kick-test \
	message-test \
	misc-test \
	mode-test \
	opless-channel-test \
	who-test \
	whois-test \
	server-link-test \
	server-login-test \
	stop-server2 \
	stress-server.sh \
	stop-server1

# -eof-
