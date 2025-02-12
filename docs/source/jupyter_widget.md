# Hypernets jupyter notebook widget

This widget is used to visualize the running process of the experiment in jupyter notebook or jupyterlab.

## Build from source code

There are two projects related to the widget:

- `hypernets-experiment`: based on [react](https://reactjs.org), experiment visualization, directory is at `js` 
- `hypernets-jupyter-widget`: python projects，jupyter notebook & jupyterlab widget, directory is at `hypernets/hn_widget`

`hypernets jupyter widget` relies on `hypernets experiment`,  to build the software environment required by the project:

- [python 3.7+](https://python.org)
- [nodejs v14.15.0+](https://nodejs.org/en/)
- [pip 20.0.2+](https://pypi.org/project/pip/)
- [jupyterlab 2.0.0+ ](https://jupyter.org/) (if you're using jupyterlab)

Clone the repo:

```bash
git clone https://github.com/DataCanvasIO/Hypernets.git
```

Build React project `hypernets-experiment`:
```bash
cd Hypernets/js
npm install yarn webpack webpack-cli -g   
npm install 
webpack # build experimentVis.js file
cp build/experimentVis.js ../hypernets/hn_widget/js/lib/
```

Build and install the widget:
```bash
cd Hypernets/hypernets/hn_widget
pip install jupyter_packaging  # jupyter_packaging is required by setup.py
pip install .  # build and install the widget
```

Enable the widget:
```bash
jupyter nbextension install --py --symlink --sys-prefix hn_widget
jupyter nbextension enable --py --sys-prefix hn_widget
```
