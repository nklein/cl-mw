
LISP_FAST_FAIL = sbcl --disable-debugger
LISP = sbcl

all: exec

debug: ping.dbg

exec: ping

ping: ping.lisp package.lisp
	echo "(require :cl-mw.examples.ping) (use-package :cl-mw.examples.ping) (mw-dump-exec :exec-name \"./ping\")" | $(LISP_FAST_FAIL)

ping.dbg: ping.lisp package.lisp
	echo "(require :cl-mw.examples.ping) (use-package :cl-mw.examples.ping) (mw-dump-exec \"./ping.dbg\")" | $(LISP)

clean:
	rm -f *.fasl *~ *.so ping ping.dbg *.rsc
