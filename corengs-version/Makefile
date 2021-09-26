PACKAGE=runtime
SCRIPTS = corengs-version
MAN = corengs-version.1
CLEANFILES = corengs-version corengs-version.sh
NEWVERS = ${SRCTOP}/sys/conf/newvers.sh

corengs-version.sh: ${.CURDIR}/corengs-version.sh.in ${NEWVERS}
	eval $$(sh ${NEWVERS} -v); \
	if ! sed -e "\
			s/@@TYPE@@/$${TYPE}/g; \
			s/@@REVISION@@/$${REVISION}/g; \
			s/@@BRANCH@@/$${BRANCH}/g; \
		" ${.CURDIR}/corengs-version.sh.in >${.TARGET} ; then \
		rm -f ${.TARGET} ; \
		exit 1 ; \
	fi

.include <bsd.prog.mk>
