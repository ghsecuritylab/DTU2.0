#
# Defines the part type that this project uses.
#
PART=__MSP432P401R__

#
# The base directory for MSPWare.
#
ROOT=../../../..

#
# Include the common make definitions.
#
include ../../Makefile.defs

#
# Where to find header files that do not live in the source directory.
#
IPATH=../../../..
IPATH+=../../../../inc/
IPATH+=../../../../inc/CMSIS/
IPATH+=../../../../driverlib/MSP432P4xx

#
# The default rule, which causes the crc32_32-bit_signature_calculation example to be built.
#
all: ${COMPILER}
all: ${COMPILER}/crc32_32-bit_signature_calculation.axf

#
# The rule to clean out all the build products.
#
clean:
	@rm -rf ${COMPILER} ${wildcard *~}

#
# The rule to create the target directory.
#
${COMPILER}:
	@mkdir -p ${COMPILER}

#
# Rules for building the crc32_32-bit_signature_calculation example.
#
${COMPILER}/crc32_32-bit_signature_calculation.axf: ${COMPILER}/startup_msp432p401r_${COMPILER}.o
${COMPILER}/crc32_32-bit_signature_calculation.axf: ${COMPILER}/system_msp432p401r.o
${COMPILER}/crc32_32-bit_signature_calculation.axf: ${COMPILER}/crc32_32-bit_signature_calculation.o
${COMPILER}/crc32_32-bit_signature_calculation.axf: ${ROOT}/driverlib/MSP432P4xx/${COMPILER}/msp432p4xx_driverlib.a
${COMPILER}/crc32_32-bit_signature_calculation.axf: crc32_32-bit_signature_calculation_gcc.ld
SCATTERgcc_crc32_32-bit_signature_calculation=crc32_32-bit_signature_calculation_gcc.ld
ENTRY_crc32_32-bit_signature_calculation=resetISR
CFLAGSgcc=-DTARGET_IS_MSP432P4XX

#
# Include the automatically generated dependency files.
#
ifneq (${MAKECMDGOALS},clean)
-include ${wildcard ${COMPILER}/*.d} __dummy__
endif
