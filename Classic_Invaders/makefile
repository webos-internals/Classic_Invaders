CC=g++
CFLAGS=-W -Wall -O3 `sdl-config --cflags` -I/usr/local/include
LIBS=`sdl-config --libs` -lSDL_image -lSDL_ttf -lSDL_mixer

cinvaders: shot.o alien.o game.o game_entity.o main.o player.o ttf.o ui.o \
  status.o bonus_ship.o sound.o
	$(CC) -o cinvaders shot.o alien.o game.o game_entity.o main.o player.o \
	ttf.o ui.o status.o bonus_ship.o sound.o $(LIBS)
alien.o: alien.cpp alien.h game.h game_entity.h screen.h
	$(CC) $(CFLAGS) -c alien.cpp
game.o: game.cpp game.h ui.h status.h sound.h game_entity.h screen.h \
  player.h alien.h shot.h bonus_ship.h explosion.h shield_piece.h rand_num_gen.h
	$(CC) $(CFLAGS) -c game.cpp
game_entity.o: game_entity.cpp game_entity.h screen.h
	$(CC) $(CFLAGS) -c game_entity.cpp
main.o: main.cpp game.h
	$(CC) $(CFLAGS) -c main.cpp
player.o: player.cpp player.h game.h game_entity.h
	$(CC) $(CFLAGS) -c player.cpp
shot.o: shot.cpp shot.h game.h game_entity.h
	$(CC) $(CFLAGS) -c shot.cpp
ttf.o: ttf.cpp ttf.h
	$(CC) $(CFLAGS) -c ttf.cpp
ui.o: ui.cpp ui.h ttf.h screen.h
	$(CC) $(CFLAGS) -c ui.cpp
status.o: status.cpp status.h screen.h
	$(CC) $(CFLAGS) -c status.cpp
bonus_ship.o: bonus_ship.cpp bonus_ship.h screen.h game_entity.h game.h 
	$(CC) $(CFLAGS) -c bonus_ship.cpp
sound.o: sound.cpp sound.h
	$(CC) $(CFLAGS) -c sound.cpp

.PHONY: clean
clean:
	for i in *.o; do rm -f $$i; done
	if [ -e cinvaders ]; then rm -f cinvaders; fi
	if [ -e cinvaders.exe ]; then rm -f cinvaders.exe; fi

