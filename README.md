# libroDelPoli
## Preparazione
- [x] Introduzione Processing
- [x] Introduzione Linux
- [x] Installazione Raspberry

## Istruzioni

### Riattivazione Autorun Player

edit /etc/rc.local ( rimuovi commenti a questa riga)

	sudo -H -u pi -s -- bash "/home/pi/Desktop/scripts/omxsyncstart.sh" &


### Per cambiare il video di riferimento e riempire lo schermo


- cambiare questa linea

> 	  omxplayer-sync -mu synctest.mp4

con

>	  omxplayer-sync -mu --aspect=fill /home/pi/Desktop/video/video.mp4


### Slave / Master
in Desktop/scripts/omxsyncstart.sh

- slave:
> sleep 60
> omxplayer-sync -lu Desktop/video/video.mp4

- master:
> sleep 30
> omxplayer-sync -mu Desktop/video/video.mp4

- indipendente:
> sleep 60
> omxplayer-sync -u Desktop/video/video.mp4
