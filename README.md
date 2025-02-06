# Filesender_setup

- documentation
https://support.aarnet.edu.au/hc/en-us/articles/5276533711887-Use-FileSender-from-the-command-line

- log into filesender with adelaide uni credectials
https://filesender.aarnet.edu.au/

- download filesender.py script from aarnet
I've copied this to 
/home/566/dt9853/projects/FileSender_setup

```bash
scp filesender.py dt9853@gadi.nci.org.au:/home/566/dt9853/projects/FileSender_setup
```

create subfolder .filesender in home on gadi

```bash
mkdir -p ~/.filesender

```
- download filesender.py.ini config file
copied to new .filesender directory
/home/566/dt9853/projects/FileSender_setup

```bash
scp filesender.py.ini dt9853@gadi.nci.org.au:/home/566/dt9853/.filesender
```

- generate a new API key
- did this in aarnet filesender, myprofile
- copied API secret
```
4650aa35a43426f653429cf20e32d836ccf727375e89a843da97ad2c7835f456
```

# Send files from the command line

```bash
python filesender.py -r [email] [files]
```
or
```bash
python filesender.py -u [username] -a [API key] -r [email] [files]
```
[username] is your FileSender username – typically your institute email address.

[API key] is the API key you retrieved from FileSender earlier.

[email] is the email address of the recipient.

[files] is the locations and names of the files you’re sending, separated by a space.

- on gadi, need to load a version of python that works
e.g
```bash
module load python3/3.12.1
python3 ~/projects/filesender/filesender.py -v -u daniel.thomson@adelaide.edu.au -a 4650aa35a43426f653429cf20e32d836ccf727375e89a843da97ad2c7835f456 -r daniel.thomson@adelaide.edu.au [files]
```
- I tried doing this on a 'screen' session but there was an error

# to generate wget command to download filesender link
https://filesender-download.streamlit.app/

