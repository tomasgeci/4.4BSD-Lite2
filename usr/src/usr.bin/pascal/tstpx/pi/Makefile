TRANSLATE = pi
EXECUTE = -px

SRCDIR = ../src
INDIR = ../in
OUTDIR = ../out

NO_INPUT = align ancestor ancestor2 \
	backtracerr bench binrdwt \
	clock cutter \
	eightqueens \
	fay ffunc fnested form fproc funcs \
	gencard gordon \
	hamachi \
	math \
	nonlocgoto numericio \
	palindromes permute \
	piextn powersoftwo \
	primes pvs1 pvs2 pvs3 \
	quicksort \
	random real realout reset \
	scaltst sequin setret shoemake \
	sort strngs \
	t01 t03 t04 t05 \
	t06 t07 t08 t09 t10 \
	t11 t12 t13 t14 t15 \
	t17 t18 t19 \
	t6.6.3.1-5 t6.6.3.4-2 \
	testeoln testio transpose \
	wnj

HAS_INPUT = basic cfor cntchars expotst hanoi hugereal index insan \
	nmaze pcerror peter pretty procs rdpal rdwt setest size t16

all: notice ${NO_INPUT} ${HAS_INPUT}

notice:
	@echo ""
	@echo "the following programs should fail during execution:"
	@echo "	pvs2, pvs3, reset, testeoln, pcerror"

clean:
	rm -f ${NO_INPUT} ${HAS_INPUT}
	rm -f \#* f file foo obj out all.list

${NO_INPUT}:
	@echo ""
	${TRANSLATE} ${SRCDIR}/$@.p
	mv obj $@
	${EXECUTE} ./$@ > out 2>&1
	-diff ${OUTDIR}/$@.out out
	cp /dev/null $@

${HAS_INPUT}:
	@echo ""
	${TRANSLATE} ${SRCDIR}/$@.p
	mv obj $@
	${EXECUTE} ./$@ < ${INDIR}/$@.in > out 2>&1
	-diff ${OUTDIR}/$@.out out
	cp /dev/null $@
