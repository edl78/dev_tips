# Development Tips

## VsCode to remote docker

### Setup
- in VsCode, install Docker and Remote-Containers extension.
- start the docker container to debug on the remote machine.
- create a docker context on the local machine, for example (change details): `docker context create docker-on-dopamine --docker "host=ssh://username@server:port"`
- setup ssh-tunneling: `ssh-keygen`
- copy with helper tool: `ssh-copy-id -p port_number -i path/to/key.pub username@server`
- make sure the ssh-agent is set up, this can be checked with `ssh-add -l`
  - if the (RSA) id does not show up refer to the VSCode documentation at: <https://code.visualstudio.com/docs/containers/ssh>
- switch to remote docker context in vscode gui docker environment.
- hit F1 and choose "Remote-Containers: Attach to running container..."
- done. Open a file and start debugging with F5 or other means. Enjoy!
- Known issue: if VsCode Python plugin fails to start debug, install an older version, 22.6.0 works for example.