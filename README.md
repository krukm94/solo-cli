# solo command line utilities

Install this on your **PC** to access some sweet Solo development utilities.

```
pip install -UI git+https://github.com/3drobotics/solo-cli
```

Your **PC** will now have a `solo` command line tool allowing you to access the following tools.

## cli

```
$ solo
Solo command line utilities.

Usage:
  solo info
  solo wifi --name=<n> --password=<p>
  solo update (solo|controller|both) (latest|<version>)
  solo revert (solo|controller|both) (latest|current|factory|<version>)
  solo provision
  solo resize
  solo logs (download)
  solo install-pip
  solo install-smart
  solo install-runit
  solo video (acquire|restore)

Options:
  -h --help        Show this screen.
  --name=<n>       WiFi network name.
  --password=<p>   WiFi password.
```

### wifi

`solo wifi` connects your Controller to a local wifi network, allowing you to develop for Solo while also enabling connection to the outside Internet.

1. Turn on your Controller. Connect your PC to to the Controller's WiFi network.
2. Run this command from your PC's command line. Specify your local wifi network and password as the `--name` and `--password` arguments.
3. Turn on (or restart) Solo.

You will now have access to the Internet on your PC, Solo, and the Controller. You can still connect to Solo and the Controller by their dedicated IP addresses (`10.1.1.1` and `10.1.1.10`), while the Controller is also assigned its own IP on your local WiFi network.

```
$ solo wifi --name="wifi ssid" --password="wifi password"
...
you are now connected to the internet.
setup complete.
```

### logs

Download logs from Solo into your current folder.

### video

* `acquire` frees `/dev/video0` for scripts to use it as a video source.
* `restore` restores the video downlink to apps, reclaiming `/dev/video0`.

## License

MIT/Apache-2.0
