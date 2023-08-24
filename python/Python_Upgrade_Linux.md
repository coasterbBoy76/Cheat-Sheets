# Python


## Checking python version:
```
python3 --version
```
[root@hostname user]# Python 3.6.8


<br>

## Setting Alternative
- Option 1.
```
alternatives --config python
```
<br>
- There are 2 programs which provide 'python'.

```
There are 2 programs which provide 'python'.

  Selection    Command
-----------------------------------------------
*+ 1           /usr/libexec/no-python
   2           /usr/bin/python3

Enter to keep the current selection[+], or type selection number:
```

<br>

- Option 2.
```
alternatives --config python3
```

<br>

- There is 1 program that provides 'python3'.
```
There is 1 program that provides 'python3'.

  Selection    Command
-----------------------------------------------
*+ 1           /usr/bin/python3.6

Enter to keep the current selection[+], or type selection number:
```
<br>

## Python Install
```
yum install python3.11
python3.11 --version
python --version
```

