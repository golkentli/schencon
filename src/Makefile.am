if BIT64CPLEXSYSTEM
SYSTEM = x86-64_sles10_4.1
else
SYSTEM = x86_sles10_4.1
endif !BIT64CPLEXSYSTEM
LIBFORMAT = static_pic

# CPLEXBASEDIR is a ./configure parameter
#CPLEXBASEDIR  = /other/ILOG/CPLEX_Studio_AcademicResearch122
CPLEXDIR      = $(CPLEXBASEDIR)/cplex
CONCERTDIR    = $(CPLEXBASEDIR)/concert
CPLEXBINDIR   = $(CPLEXDIR)/bin/$(BINDIST)
CPLEXLIBDIR   = $(CPLEXDIR)/lib/$(SYSTEM)/$(LIBFORMAT)
CONCERTLIBDIR = $(CONCERTDIR)/lib/$(SYSTEM)/$(LIBFORMAT)
CONCERTINCDIR = $(CONCERTDIR)/include
CPLEXINCDIR   = $(CPLEXDIR)/include


INCLUDES = -I$(CPLEXINCDIR) -I$(CONCERTINCDIR)
AM_CPPFLAGS = -Wall -g -O -fPIC -fexceptions -DNDEBUG -DIL_STD
AM_LDFLAGS = -L$(CPLEXLIBDIR) -L$(CONCERTLIBDIR) -pthread
if !BIT64CPLEXSYSTEM
AM_CPPFLAGS += -m32
AM_LDFLAGS += -m32
endif !BIT64CPLEXSYSTEM
LDADD = -lilocplex -lcplex -lconcert -lm

bin_PROGRAMS    = ilpsec problemcreator heursec plotpeaks validateschedule
#lib_LIBRARIES   = libfoo1.a libfoo2.a libfoo3.a ....
#check_PROGRAMS  = test1 test2 test3 ....
#TESTS           = $(check_PROGRAMS)
#include_HEADERS = header1.h header2.h ....


ilpsec_SOURCES = ILPScheduler.cpp \
		 ILPScheduler.h \
		 ILPSchedulerMain.cpp \
		 SchedulingProblem.h \
		 SchedulingProblem.cpp \
		 SchedulingProblemReader.h \
		 SchedulingProblemReader.cpp \
		 SchedulingSolution.h \
		 SchedulingSolution.cpp \
		 InfeasibleSolutionException.h \
		 SchedulingSolutionStatusAdapter.h \
		 Task.h \
		 Task.cpp \
		 util.h \
		 Signal.h

ilpsec_LDADD   = $(LDADD) 
#ilpsec_LDFLAGS = $(AM_LDFLAGS)
#prog1_DEPENDENCIES = dep1 dep2 dep3 ...

problemcreator_SOURCES = ProblemCreatorMain.cpp \
			 Task.h \
			 Task.cpp \
			 SchedulingProblem.h \
			 SchedulingProblem.cpp \
			 util.h

problemcreator_LDADD   = 

heursec_SOURCES = HeuristicsBasedSchedulerMain.cpp \
		  SchedulingProblem.h \
		  SchedulingProblem.cpp \
		  SchedulingProblemReader.h \
		  SchedulingProblemReader.cpp \
		  SchedulingMOMHSolution.hpp \
		  SchedulingMOMHSolution.cpp \
		  Signal.h \
		  Tab.h \
		  Task.h \
		  Task.cpp \
		  util.h \
		  ILPScheduler.cpp \
		  ILPScheduler.h \
		  InfeasibleSolutionException.h \
		  SchedulingSolutionStatusAdapter.h \
		  SchedulingSolution.h \
		  SchedulingSolution.cpp \
		  SchedulingProblemResult.h \
		  SchedulingProblemResult.cpp 

heursec_LDADD = $(LIBMOMH_LIBS) $(LDADD)

heursec_CXXFLAGS = $(LIBMOMH_CFLAGS)


plotpeaks_SOURCES = PlotPeaksMain.cpp \
		  SchedulingProblem.h \
		  SchedulingProblem.cpp \
		  SchedulingProblemReader.h \
		  SchedulingProblemReader.cpp \
		  SchedulingMOMHSolution.hpp \
		  SchedulingMOMHSolution.cpp \
		  Signal.h \
		  Tab.h \
		  Task.h \
		  Task.cpp \
		  util.h \
		  ILPScheduler.cpp \
		  ILPScheduler.h \
		  InfeasibleSolutionException.h \
		  SchedulingSolutionStatusAdapter.h \
		  SchedulingSolution.h \
		  SchedulingSolution.cpp \
		  SchedulingProblemResult.h \
		  SchedulingProblemResult.cpp 

plotpeaks_LDADD = $(LIBMOMH_LIBS) $(LDADD)

plotpeaks_CXXFLAGS = $(LIBMOMH_CFLAGS)



validateschedule_SOURCES = ScheduleValidationTest.cpp \
			   util.h \
			   Signal.h \
			   Task.h \
		 	   Task.cpp
