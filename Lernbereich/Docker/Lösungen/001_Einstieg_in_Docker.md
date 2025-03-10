# Lösungen für die Sektion 001 Einstieg in Docker

1. `docker images`
2. `docker pull dockerhub.registry.domain.de/debian:12.5`
3. `docker images`
4. `docker ps`
5. `docker ps -a`
6. `docker run -itd --name gruess-gott-debian dockerhub.registry.domain.de/debian:12.5`
7. `docker ps`
8. `docker ps -a`
9. Nein
10. `docker run --name gruess-gott-debian dockerhub.registry.domain.de/debian:12.5`
11. `docker run -it --name gruess-gott-debian-2 dockerhub.registry.domain.de/debian:12.5`
12. `mkdir test`
13. `cd test` -> `touch test-1.txt`
14. `apt update` + `apt install 'nano/vim' -y`
15. `nano/vim test-1.txt`
16. Drücke `ctrl + p` und danach `ctrl + q`
17. `docker stop gruess-gott(-2)`
18. `docker container rm gruess-gott(-2)`
19. `docker run -it --name gruess-gott-debian-2 dockerhub.registry.domain.de/debian:12.5`
