Haskell, Yesod, Vagrant, and Heroku
-----------------------------------

- Inspired by https://github.com/yesodweb/yesod/wiki/Deploying-Yesod-Apps-to-Heroku and http://www.yesodweb.com/blog/2011/07/haskell-on-heroku I want to develop a Yesod web app on a VM that resembles a Heroku Cedar instance
- https://groups.google.com/forum/#!msg/yesodweb/BrQPVNXqRlo/smPMX8N__K0J suggests that I can't really develop Yesod on 64-bit GHC on OS X -- a Vagrant box is recommended

Setting up Vagrant
~~~~~~~~~~~~~~~~~~

The box comes from https://dl.dropboxusercontent.com/s/rnc0p8zl91borei/heroku.box

I downloaded it in the browser.

A copy of VagrantFile is included in this repository