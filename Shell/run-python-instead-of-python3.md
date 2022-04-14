My Linux Terminal does not recognize the command `python`, only `python3` which makes it tiresome to type repeatedly. 

To solve that:
- Install the [`python-is-python3`](https://packages.ubuntu.com/search?keywords=python-is-python3) package:
```python
sudo apt install python-is-python3
```
- This allows shell to run the command `python` as latest `python3` version

Source: ([python3 - How to make 'python' program command execute Python 3? - Ask Ubuntu](https://askubuntu.com/questions/320996/how-to-make-python-program-command-execute-python-3))