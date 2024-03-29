# use normal make for this Makefile
#
# Makefile for building user programs to run on top of Nachos
#
# Several things to be aware of:
#
#    Nachos assumes that the location of the program startup routine (the
# 	location the kernel jumps to when the program initially starts up)
#       is at location 0.  This means: start.o must be the first .o passed
# 	to ld, in order for the routine "Start" to be loaded at location 0
#

# If you are running on SunOS 5.x machines, uncomment the next line
GCCDIR = ../gnu/
LDFLAGS = -T newscript -N
ASFLAGS = -mips1
CPPFLAGS = $(INCDIR)

# if you aren't cross-compiling:
# GCCDIR =
# LDFLAGS = -N -T 0
# ASFLAGS =
# CPPFLAGS = -P $(INCDIR)


CC = $(GCCDIR)gcc
AS = $(GCCDIR)as
LD = $(GCCDIR)ld
CPP = $(GCCDIR)cpp

INCDIR =-I../userprog -I../threads
CFLAGS = -G 0 -c $(INCDIR)

all: halt matmult sort testfiles exectests forktests manager senator customer applicationClerk pictureClerk passportClerk cashier passportoffice passportofficeManager passportofficeClerks passportofficeCustomers passportofficeSenators locktest condtest twoMatmults testsend networkTestsuite lockInvalidTest lock_t1 lock_t2 condServerInitTest condServer_t2 condServer_t1 condServer_t3 condServer_t4 condInit monInit monServer_t1 monServer_t2 monServer_t3 unitTestCond2 unitTestCond1 lock_t4 lock_t3 acquireTest signalTest twoSorts forkTwoSorts forkTwoMatmults signalTestEnd

start.o: start.s ../userprog/syscall.h
	$(CPP) $(CPPFLAGS) start.s > strt.s
	$(AS) $(ASFLAGS) -o start.o strt.s
	rm strt.s

halt.o: halt.c
	$(CC) $(CFLAGS) -c halt.c
halt: halt.o start.o
	$(LD) $(LDFLAGS) start.o halt.o -o halt.coff
	../bin/coff2noff halt.coff halt

sort.o: sort.c
	$(CC) $(CFLAGS) -c sort.c
sort: sort.o start.o
	$(LD) $(LDFLAGS) start.o sort.o -o sort.coff
	../bin/coff2noff sort.coff sort

twoSorts.o: twoSorts.c
	$(CC) $(CFLAGS) -c twoSorts.c
twoSorts: twoSorts.o start.o
	$(LD) $(LDFLAGS) start.o twoSorts.o -o twoSorts.coff
	../bin/coff2noff twoSorts.coff twoSorts

forkTwoSorts.o: forkTwoSorts.c
	$(CC) $(CFLAGS) -c forkTwoSorts.c
forkTwoSorts: forkTwoSorts.o start.o
	$(LD) $(LDFLAGS) start.o forkTwoSorts.o -o forkTwoSorts.coff
	../bin/coff2noff forkTwoSorts.coff forkTwoSorts

matmult.o: matmult.c
	$(CC) $(CFLAGS) -c matmult.c
matmult: matmult.o start.o
	$(LD) $(LDFLAGS) start.o matmult.o -o matmult.coff
	../bin/coff2noff matmult.coff matmult


twoMatmults.o: twoMatmults.c
	$(CC) $(CFLAGS) -c twoMatmults.c
twoMatmults: twoMatmults.o start.o
	$(LD) $(LDFLAGS) start.o twoMatmults.o -o twoMatmults.coff
	../bin/coff2noff twoMatmults.coff twoMatmults

forkTwoMatmults.o: forkTwoMatmults.c
	$(CC) $(CFLAGS) -c forkTwoMatmults.c
forkTwoMatmults: forkTwoMatmults.o start.o
	$(LD) $(LDFLAGS) start.o forkTwoMatmults.o -o forkTwoMatmults.coff
	../bin/coff2noff forkTwoMatmults.coff forkTwoMatmults

testfiles.o: testfiles.c
	$(CC) $(CFLAGS) -c testfiles.c
testfiles: testfiles.o start.o
	$(LD) $(LDFLAGS) start.o testfiles.o -o testfiles.coff
	../bin/coff2noff testfiles.coff testfiles

exectests.o: exectests.c
		$(CC) $(CFLAGS) -c exectests.c
exectests: exectests.o start.o
		$(LD) $(LDFLAGS) start.o exectests.o -o exectests.coff
		../bin/coff2noff exectests.coff exectests

forktests.o: forktests.c
				$(CC) $(CFLAGS) -c forktests.c
forktests: forktests.o start.o
				$(LD) $(LDFLAGS) start.o forktests.o -o forktests.coff
				../bin/coff2noff forktests.coff forktests



setup.o: setup.h
				$(CC) $(CFLAGS) -c setup.c

manager.o: manager.c
					$(CC) $(CFLAGS) -c manager.c
manager: manager.o start.o setup.o
				$(LD) $(LDFLAGS) start.o manager.o setup.o -o manager.coff
				../bin/coff2noff manager.coff manager
senator.o: senator.c
				$(CC) $(CFLAGS) -c senator.c
senator: senator.o start.o setup.o
				$(LD) $(LDFLAGS) start.o senator.o setup.o -o senator.coff
				../bin/coff2noff senator.coff senator
customer.o: customer.c
			$(CC) $(CFLAGS) -c customer.c
customer: customer.o start.o setup.o
				$(LD) $(LDFLAGS) start.o customer.o setup.o -o customer.coff
				../bin/coff2noff customer.coff customer
cashier.o: cashier.c
				$(CC) $(CFLAGS) -c cashier.c
cashier: cashier.o start.o setup.o
				$(LD) $(LDFLAGS) start.o cashier.o setup.o -o cashier.coff
				../bin/coff2noff cashier.coff cashier
applicationClerk.o: applicationClerk.c
				$(CC) $(CFLAGS) -c applicationClerk.c
applicationClerk: applicationClerk.o start.o setup.o
				$(LD) $(LDFLAGS) start.o applicationClerk.o setup.o -o applicationClerk.coff
				../bin/coff2noff applicationClerk.coff applicationClerk
pictureClerk.o: pictureClerk.c
				$(CC) $(CFLAGS) -c pictureClerk.c
pictureClerk: pictureClerk.o start.o setup.o
				$(LD) $(LDFLAGS) start.o pictureClerk.o setup.o -o pictureClerk.coff
				../bin/coff2noff pictureClerk.coff pictureClerk
passportClerk.o: passportClerk.c
				$(CC) $(CFLAGS) -c passportClerk.c
passportClerk: passportClerk.o start.o setup.o
				$(LD) $(LDFLAGS) start.o passportClerk.o setup.o -o passportClerk.coff
				../bin/coff2noff passportClerk.coff passportClerk

passportoffice.o: passportoffice.c
				$(CC) $(CFLAGS) -c passportoffice.c
passportoffice: passportoffice.o start.o setup.o
				$(LD) $(LDFLAGS) start.o passportoffice.o setup.o -o passportoffice.coff
				../bin/coff2noff passportoffice.coff passportoffice

passportofficeManager.o: passportofficeManager.c
				$(CC) $(CFLAGS) -c passportofficeManager.c
passportofficeManager: passportofficeManager.o start.o setup.o
				$(LD) $(LDFLAGS) start.o passportofficeManager.o setup.o -o passportofficeManager.coff
				../bin/coff2noff passportofficeManager.coff passportofficeManager
passportofficeClerks.o: passportofficeClerks.c
				$(CC) $(CFLAGS) -c passportofficeClerks.c
passportofficeClerks: passportofficeClerks.o start.o setup.o
				$(LD) $(LDFLAGS) start.o passportofficeClerks.o setup.o -o passportofficeClerks.coff
				../bin/coff2noff passportofficeClerks.coff passportofficeClerks
passportofficeCustomers.o: passportofficeCustomers.c
				$(CC) $(CFLAGS) -c passportofficeCustomers.c
passportofficeCustomers: passportofficeCustomers.o start.o setup.o
				$(LD) $(LDFLAGS) start.o passportofficeCustomers.o setup.o -o passportofficeCustomers.coff
				../bin/coff2noff passportofficeCustomers.coff passportofficeCustomers
passportofficeSenators.o: passportofficeSenators.c
				$(CC) $(CFLAGS) -c passportofficeSenators.c
passportofficeSenators: passportofficeSenators.o start.o setup.o
				$(LD) $(LDFLAGS) start.o passportofficeSenators.o setup.o -o passportofficeSenators.coff
				../bin/coff2noff passportofficeSenators.coff passportofficeSenators

locktest.o: locktest.c
				$(CC) $(CFLAGS) -c locktest.c
locktest: locktest.o start.o
				$(LD) $(LDFLAGS) start.o locktest.o -o locktest.coff
				../bin/coff2noff locktest.coff locktest

condtest.o: condtest.c
				$(CC) $(CFLAGS) -c condtest.c
condtest: condtest.o start.o
				$(LD) $(LDFLAGS) start.o condtest.o -o condtest.coff
				../bin/coff2noff condtest.coff condtest

testsend.o: testsend.c
				$(CC) $(CFLAGS) -c testsend.c
testsend: testsend.o start.o
				$(LD) $(LDFLAGS) start.o testsend.o -o testsend.coff
				../bin/coff2noff testsend.coff testsend

networkTestsuite.o: networkTestsuite.c
				$(CC) $(CFLAGS) -c networkTestsuite.c
networkTestsuite: networkTestsuite.o start.o
				$(LD) $(LDFLAGS) start.o networkTestsuite.o -o networkTestsuite.coff
				../bin/coff2noff networkTestsuite.coff networkTestsuite

lock_t1.o: lock_t1.c
				$(CC) $(CFLAGS) -c lock_t1.c
lock_t1: lock_t1.o start.o
				$(LD) $(LDFLAGS) start.o lock_t1.o -o lock_t1.coff
				../bin/coff2noff lock_t1.coff lock_t1

lock_t2.o: lock_t2.c
				$(CC) $(CFLAGS) -c lock_t2.c
lock_t2: lock_t2.o start.o
				$(LD) $(LDFLAGS) start.o lock_t2.o -o lock_t2.coff
				../bin/coff2noff lock_t2.coff lock_t2
lock_t3.o: lock_t3.c
				$(CC) $(CFLAGS) -c lock_t3.c
lock_t3: lock_t3.o start.o
				$(LD) $(LDFLAGS) start.o lock_t3.o -o lock_t3.coff
				../bin/coff2noff lock_t3.coff lock_t3

lock_t4.o: lock_t4.c
				$(CC) $(CFLAGS) -c lock_t4.c
lock_t4: lock_t4.o start.o
				$(LD) $(LDFLAGS) start.o lock_t4.o -o lock_t4.coff
				../bin/coff2noff lock_t4.coff lock_t4

lockInvalidTest.o: lockInvalidTest.c
				$(CC) $(CFLAGS) -c lockInvalidTest.c
lockInvalidTest: lockInvalidTest.o start.o
				$(LD) $(LDFLAGS) start.o lockInvalidTest.o -o lockInvalidTest.coff
				../bin/coff2noff lockInvalidTest.coff lockInvalidTest

condServerInitTest.o: condServerInitTest.c
				$(CC) $(CFLAGS) -c condServerInitTest.c
condServerInitTest: condServerInitTest.o start.o
				$(LD) $(LDFLAGS) start.o condServerInitTest.o -o condServerInitTest.coff
				../bin/coff2noff condServerInitTest.coff condServerInitTest

condServer_t2.o: condServer_t2.c
				$(CC) $(CFLAGS) -c condServer_t2.c
condServer_t2: condServer_t2.o start.o
				$(LD) $(LDFLAGS) start.o condServer_t2.o -o condServer_t2.coff
				../bin/coff2noff condServer_t2.coff condServer_t2

condServer_t1.o: condServer_t1.c
				$(CC) $(CFLAGS) -c condServer_t1.c
condServer_t1: condServer_t1.o start.o
				$(LD) $(LDFLAGS) start.o condServer_t1.o -o condServer_t1.coff
				../bin/coff2noff condServer_t1.coff condServer_t1

condInit.o: condInit.c
				$(CC) $(CFLAGS) -c condInit.c
condInit: condInit.o start.o
				$(LD) $(LDFLAGS) start.o condInit.o -o condInit.coff
				../bin/coff2noff condInit.coff condInit

condServer_t3.o: condServer_t3.c
				$(CC) $(CFLAGS) -c condServer_t3.c
condServer_t3: condServer_t3.o start.o
				$(LD) $(LDFLAGS) start.o condServer_t3.o -o condServer_t3.coff
				../bin/coff2noff condServer_t3.coff condServer_t3

condServer_t4.o: condServer_t4.c
				$(CC) $(CFLAGS) -c condServer_t4.c
condServer_t4: condServer_t4.o start.o
				$(LD) $(LDFLAGS) start.o condServer_t4.o -o condServer_t4.coff
				../bin/coff2noff condServer_t4.coff condServer_t4

monServer_t1.o: monServer_t1.c
			$(CC) $(CFLAGS) -c monServer_t1.c
monServer_t1: monServer_t1.o start.o
			$(LD) $(LDFLAGS) start.o monServer_t1.o -o monServer_t1.coff
			../bin/coff2noff monServer_t1.coff monServer_t1

monServer_t2.o: monServer_t2.c
				$(CC) $(CFLAGS) -c monServer_t2.c
monServer_t2: monServer_t2.o start.o
				$(LD) $(LDFLAGS) start.o monServer_t2.o -o monServer_t2.coff
				../bin/coff2noff monServer_t2.coff monServer_t2

monServer_t3.o: monServer_t3.c
				$(CC) $(CFLAGS) -c monServer_t3.c
monServer_t3: monServer_t3.o start.o
				$(LD) $(LDFLAGS) start.o monServer_t3.o -o monServer_t3.coff
				../bin/coff2noff monServer_t3.coff monServer_t3

monInit.o: monInit.c
				$(CC) $(CFLAGS) -c monInit.c
monInit: monInit.o start.o
				$(LD) $(LDFLAGS) start.o monInit.o -o monInit.coff
				../bin/coff2noff monInit.coff monInit

unitTestCond1.o: unitTestCond1.c
				$(CC) $(CFLAGS) -c unitTestCond1.c
unitTestCond1: unitTestCond1.o start.o
				$(LD) $(LDFLAGS) start.o unitTestCond1.o -o unitTestCond1.coff
				../bin/coff2noff unitTestCond1.coff unitTestCond1

unitTestCond2.o: unitTestCond2.c
				$(CC) $(CFLAGS) -c unitTestCond2.c
unitTestCond2: unitTestCond2.o start.o
				$(LD) $(LDFLAGS) start.o unitTestCond2.o -o unitTestCond2.coff
				../bin/coff2noff unitTestCond2.coff unitTestCond2

acquireTest.o: acquireTest.c
				$(CC) $(CFLAGS) -c acquireTest.c
acquireTest: acquireTest.o start.o
				$(LD) $(LDFLAGS) start.o acquireTest.o -o acquireTest.coff
				../bin/coff2noff acquireTest.coff acquireTest

signalTestEnd.o: signalTestEnd.c
				$(CC) $(CFLAGS) -c signalTestEnd.c
signalTestEnd: signalTestEnd.o start.o
				$(LD) $(LDFLAGS) start.o signalTestEnd.o -o signalTestEnd.coff
				../bin/coff2noff signalTestEnd.coff signalTestEnd

signalTest.o: signalTest.c
				$(CC) $(CFLAGS) -c signalTest.c
signalTest: signalTest.o start.o
				$(LD) $(LDFLAGS) start.o signalTest.o -o signalTest.coff
				../bin/coff2noff signalTest.coff signalTest




clean:
	rm -f *.o *.coff
