# TODO 14: Remove mysqrt.cxx from the list of sources

add_library(MathFunctions
            MathFunctions.cxx)

# TODO 7: Create a variable USE_MYMATH using option and set default to ON
option(USE_MYMATH "Use my own math functions." ON)

# TODO 12: When USE_MYMATH is ON, add a library for SqrtLibrary with
# source mysqrt.cxx
if(USE_MYMATH)
  target_compile_definitions(MathFunctions PRIVATE USE_MYMATH)
  add_library(SqrtLibrary STATIC
              mysqrt.cxx)
  target_link_libraries(MathFunctions PRIVATE SqrtLibrary )
endif()
