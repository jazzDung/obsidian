- Chỉnh độ sáng màn hình
	```bash
	xrandr -q | grep " connected"
	xrandr --output VGA1 --brightness 0.63
	```

- Tạo Jupyter server cho vscode.dev
	```bash
	jupyter notebook --no-browser --NotebookApp.allow_origin_pat=https://.*vscode-cdn\.net
	```
