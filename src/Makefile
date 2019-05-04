OBJS = bank0.asm
OBJS_NAME = bank0

OBJ_NAME = gb

ASM = rgbasm
LINK = rgblink
FIX = rgbfix

BDIR = build

all : $(OBJS)
	mkdir -p $(BDIR)
	$(ASM) -o$(OBJS_NAME).obj $(OBJS)
	$(LINK) -m$(BDIR)/$(OBJ_NAME).map -n$(BDIR)/$(OBJ_NAME).sym -o$(BDIR)/$(OBJ_NAME).gb $(OBJS_NAME).obj
	$(FIX) -v $(BDIR)/$(OBJ_NAME).gb
	rm $(OBJS_NAME).obj

allrun:
	make
	gambatte --force-dmg --scale 6 gb.gb
