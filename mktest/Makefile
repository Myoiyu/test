VPATH = src include
CPPFLAGES = -I include

SOURCES = count_words.c \
	 lexer.c \
	 counter.c

count_words:count_words.o lexer.o -lfl
count_words.o:counter.h
counter.o:counter.h lexer.h
lexer.o:lexer.h

include $(subst .c,.d,$(SOURCES))

%.d: %.c
	$(CC) -M $(CPPFLAGES) $< > $@.$$$$; \
	sed 's,\($*\)\.o[ :]*,\1.o $@ : ,g' < $@.$$$$ > $@;  \
	rm -f $@.$$$$
