# Setting Up Quadlet Files and Starting Services

## Copy the Quadlet Files to the Correct Directory

Place the `.container` files into `/etc/containers/systemd/`

```
sudo cp x11-init-container.container /etc/containers/systemd/
sudo cp wallboard-container.container /etc/containers/systemd/
```

## Reload the Systemd Daemon

Reload the systemd daemon to recognize the new Quadlet files.

```
sudo systemctl daemon-reload
```

## Start the Services in the Correct Order

First, start the `wallboard-pod` service:

```
sudo systemctl start wallboard-pod.pod
```

Then, start the `x11-init-container` service:

```
sudo systemctl start x11-init-container.container
```

Finally, start the `wallboard-container` service:

```
sudo systemctl start wallboard-container.container
```
