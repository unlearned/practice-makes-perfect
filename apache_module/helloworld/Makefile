##
##  Makefile -- Build procedure for sample helloworld Apache module
##  Autogenerated via ``apxs -n helloworld -g''.
##

#   the used tools
APXS=apxs
APACHECTL=apachectl

#   additional user defines, includes and libraries
#DEF=-Dmy_define=my_value
#INC=-Imy/include/dir
#LIB=-Lmy/lib/dir -lmylib

#   the default target
all: mod_helloworld.so

#   compile the DSO file
mod_helloworld.so: mod_helloworld.c
	$(APXS) -c $(DEF) $(INC) $(LIB) mod_helloworld.c

#   install the DSO file into the Apache installation
#   and activate it in the Apache configuration
install: all
	$(APXS) -i -a -n 'helloworld' mod_helloworld.so

#   cleanup
clean:
	-rm -f mod_helloworld.o mod_helloworld.so

#   simple test
test: reload
	lynx -mime_header http://localhost/helloworld

#   reload the module by installing and restarting Apache
reload: install restart

#   the general Apache start/restart/stop procedures
start:
	$(APACHECTL) start
restart:
	$(APACHECTL) restart
stop:
	$(APACHECTL) stop

