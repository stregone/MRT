#
# $Id: Makefile,v 1.1.1.1 2000/08/14 18:46:15 labovit Exp $
#

include ../../Make.include

GOAL   = route_btoa
OBJS   = route_btoa.o $(BGPLIB) $(MRTLIB)


all: $(GOAL)

$(GOAL): $(OBJS) 
#	@echo "Linking: $(LD) $(LDFLAGS) $(OBJS) -o $@"
	$(LD) $(LDFLAGS) $(OBJS) -o $@ $(SYS_LIBS)
#	@$(CP) ./$@ $(EXEC_PREFIX)/bin	
#	@$(CP) ./route_btoa.pl $(EXEC_PREFIX)/bin

$(GOAL).purify:	$(OBJS)
	$(PURIFY) -log-file=./p.log $(LD) $(LDFLAGS) $(OBJS) -o $@ $(SYS_LIBS)

install: $(GOAL)
	$(INSTALL) -m 755 $(GOAL) $(DESTDIR)/$(GOAL)

clean:
	$(RM) *.o core *.core *~* $(GOAL) $(GOAL).purify

depend:
	$(MAKEDEP) $(CFLAGS) $(CPPFLAGS) $(DEFINES) *.c


# DO NOT DELETE THIS LINE -- make depend depends on it.
