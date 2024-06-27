# Makefile
#
# Generic Linux/Unix Makefile for ProteinEvolver.
# 
# Much taken from Joe Felsenstein's PHYLIP makefiles.


PROGRAM_NAME = ProteinEvolver
VERSION = 2.2.0
FILES = Makefile parameters 
EXEDIR  = ../exe
CMP = gcc -c
LD = gcc 
LIBRARIES = -lm
FLAGS = -O3 -Wall
# for fast compile disable (#) the option one above and enable the one below
#FLAGS = -fast -Wall


#  The first target it executed if you just type "make".  It tells you how to
#  use the Makefile.

help:
	@echo ""
	@echo " To use the $(PROGRAM_NAME) Makefile, type"
	@echo "     make install       to compile the whole package and install"
	@echo "                          the executables in $(EXEDIR), and then"
	@echo "                          remove the object files to save space"
	@echo "     make all           to compile the whole package but not install it"
	@echo "                          or remove the object files"
	@echo "     make put           to move the executables into $(EXEDIR)"
	@echo "     make clean         to remove all object files and executables from the"
	@echo "                          current directory"
	@echo " "

introduce:
	@echo "Building $(PROGRAM_NAME) version $(VERSION)"

all: introduce  $(PROGRAM_NAME)$(VERSION)  
	@echo "Finished compiling."
	@echo ""

install: all put clean
	@echo "Done."
	@echo ""

put:
	@echo "Installing $(PROGRAM_NAME)$(VERSION) binaries in $(EXEDIR)"
	@mkdir -p $(EXEDIR)
	@cp $(PROGRAM_NAME)$(VERSION) $(EXEDIR)
	@echo "Finished installation."
	@echo ""

clean:
	@echo "Removing object and executable files to save space"
	@rm -f *.o *~ $(PROGRAM_NAME)$(VERSION) $(PROGRAM_NAME)-$(VERSION).tar.gz $(PROGRAM_NAME)-$(VERSION).zip
	@echo "Finished cleanup."
	@echo ""

distribution:
	@mkdir $(PROGRAM_NAME)-$(VERSION)
	@cp *.c $(FILES) $(PROGRAM_NAME)-$(VERSION)/
	@rm -f $(PROGRAM_NAME)-$(VERSION).tar.gz $(PROGRAM_NAME)-$(VERSION).zip
	@tar cvf $(PROGRAM_NAME)-$(VERSION).tar $(PROGRAM_NAME)-$(VERSION)/*
	@gzip $(PROGRAM_NAME)-$(VERSION).tar
	@zip $(PROGRAM_NAME)-$(VERSION).zip $(PROGRAM_NAME)-$(VERSION)/*
	@rm -f $(PROGRAM_NAME)-$(VERSION)/*
	@rmdir $(PROGRAM_NAME)-$(VERSION)
	@echo "distribution made."
	@echo ""

#Êthe program
$(PROGRAM_NAME)$(VERSION): $(PROGRAM_NAME)$(VERSION).o 
	$(LD) $(LIBRARIES) $(FLAGS) -o $(PROGRAM_NAME)$(VERSION) $(PROGRAM_NAME)$(VERSION).o 

$(PROGRAM_NAME)$(VERSION).o : $(PROGRAM_NAME)$(VERSION).c 
	$(CMP) $(FLAGS) $(PROGRAM_NAME)$(VERSION).c

