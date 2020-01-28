# rat-apps

Tools for analysis of rat behavioral experiments.

### Installing

Requires Python 3.  

Once Python 3 is installed, Install by installing package with `pip`. In a command line change directories to this folder, ie. one containing `setup.py` and run `pip install .`.  This will install Xmaze.py to the python scripts folder which can then be run.

### Dist on windows

To create a folder with .exe files that can be run on any Windows computer without needing to install Python, run the `dist-windows.sh` script using git bash.  ie.
```bash
bash dist-windows.sh
```
or equivalently,
```bash
make dist-windows
```

### Dist on OSX

By default, looks for Python 3 at `/usr/local/bin/python3`, this was to use `brew` Python over Anaconda Python.  If this path is incorrect, edit the top of `dist-osx.sh`.

Then run from this directory
```bash
bash dist-osx.sh
```
or equivalently
```
make dist-osx
```

#### On fresh install of Catalina

open terminal type `git`, this promptes developer tools to install.  Install git and python 3.  Then checkout repo, set `$PY=python3` and run `dist-osx.sh`.





### Updating apps for Python 3 + opencv-python

- Add brackets to `print` statements
- `QtGui.QFileDialog.getOpenFileName()` to  `QtGui.QFileDialog.getOpenFileName()[0]`
- `_,cnts,_= cv2.findContours(` to `cnts, _ = cv2.findContours(`
- In `nextFrameSlot()` changed if from
  - `#if nframe < (self.length - 10):` to
  - `if nframe < (self.frame_end - 10):`
  - for timer bug
<<<<<<< Updated upstream
=======
- `adjust_gamma` has bug where `gamma` can be 0

>>>>>>> Stashed changes
