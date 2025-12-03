Repro for mitogen apt issue
==

1. install docker
2. in ./docker/ folder, run

```
docker build -t my_ssh_image .
```

3. then run

```
docker run -d -p 2222:22 my_ssh_image
```

4. install uv

5. go to ./playbooks

6. run

```
uv run ansible-playbook -i inventory.ini playbook.yaml
```

this will now fail in the last step, if run with mitogen; or it will succeed, if without mitogen.

7. if you want to try again (to try disable mitogen, experiment, etc), you need to first remove the docker (`docker ps` and `docker kill <ID>`), then run new one

```
docker run -d -p 2222:22 my_ssh_image
```