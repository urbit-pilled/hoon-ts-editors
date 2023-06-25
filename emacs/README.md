## Emacs Hoon support

### Manual Method

1. Clone the [`hoon-ts-mode`](https://github.com/urbit-pilled/hoon-ts-mode.git) repo using:
```
git clone https://github.com/urbit-pilled/hoon-ts-mode.git
```

2. add the following to your `init.el` config file:
```
(add-to-list 'load-path "PATH-TO-HOON-REPO")
(require 'hoon-ts-mode)
```

3. Run `cd hoon-ts-mode && git pull` to download updates.