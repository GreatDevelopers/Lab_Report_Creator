cmake_minimum_required(VERSION 3.0)

# Main Step 0: Add CMake dependencies
# ------------------------------------------------------------------------------------------------------
MESSAGE(STATUS "Adding CMake modules...")
LIST(APPEND CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}/cmake/Modules/cmake-pandocology")
INCLUDE(pandocology)
INCLUDE(cmspandoc)

# Main Step I: Create main project
# -------------------------------------------------------------------------------
file(READ src/description.md desc)
file(READ src/input.txtinput)
file(READ src/output.txt output)
#execute_process(
#	COMMAND mmdc -i src/img.mmd -o src/img.png
#	)

file(WRITE src/finaloutput.md    ${desc}
	"\n# FLOW CHART\n"
	"![FLOW CHART\n](./src/img.png)"
	"\n# CODE\n"
	${code}
	"\n# INPUT\n"
	${input}
	"\n# OUTPUT\n"
	${output}
	)
add_document(
    TARGET		finaloutput
    OUTPUT_FILE 	finaloutput.pdf
    SOURCES		src/finaloutput.md
    PANDOC_DIRECTIVES 	${PANDOC_PDF_CONFIG}
)
