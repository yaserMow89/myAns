**Command Vs Shell**</br>
Why use shell instead of command? Ansible’s command module is the
preferred option for running commands on a host (when an Ansible module
won’t suffice), and it works in most scenarios. However, command doesn’t
run the command via the remote shell /bin/sh, so options like <, >, |, and &,
and local environment variables like $HOME won’t work. shell allows you
to pipe command output to other commands, access the local environment,
etc.
There are two other modules which assist in executing shell commands
remotely: script executes shell scripts (though it’s almost always a better
idea to convert shell scripts into idempotent Ansible playbooks!), and raw
executes raw commands via SSH (it should only be used in circumstances
where you can’t use one of the other options).