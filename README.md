# Assignment3

## Part1

### Step1

Create a new system user with the following:
- Home directory located at `var/lib/webgen`.
- System user login shell.
- Sub directories bin and HTML.
- The generate_index file inside `webgen/bin`.
- The index.html file inside `webgen/HTML`.
- Ownership of home directory and any files and sub directories within.

```bash
sudo useradd -r webgen -d /var/lib/webgen -s /usr/bin/nologin
```

`-r` : specifies that it is a system user.

`-d` : specifies the location of the home directory.

`-s` : specifies the shell of the user. System users usually have non-login shells.

Since the user's home directory does not exist yet, run the following command.

```bash
sudo mkdir -p /var/lib/webgen
```

`-p` : Makes directories within directories.

The following command will create two sub directories called `bin` and `HTML` inside the webgen directory.

```bash
sudo mkdir -p /var/lib/webgen/{bin,HTML}
```

To move the `generate_index` file inside the `webgen/bin` directory, run the following.

```bash
sudo mv generate_index /var/lib/webgen/bin
```

Now put an `index.html` file inside the HTML directory.

```bash
sudo touch /var/lib/webgen/HTML/index.html
```

To give ownership of the webgen directory and any files or sub directories inside it to webgen, run;

```bash
sudo chown -R webgen:webgen /var/lib/webgen
```
