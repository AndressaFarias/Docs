# Deployment does not have minimum availability.


## Mensagem POD : Error
    CrashLoopBackOff: Back-off 5m0s restarting failed container=mx-front pod=mx-front-deployment-f6b944588-bzzjq_compasso-mx-dev(d8e9ed7e-2fd8-4568-94cb-d33481a1f214)

    Log do POD

    ```
    > frontendreceitas@0.1.0 start /usr/app
> react-scripts start
There might be a problem with the project dependency tree.
It is likely not a bug in Create React App, but something you need to fix locally.
The react-scripts package provided by Create React App requires a dependency:
  "webpack": "4.41.2"
Don't try to install it manually: your package manager does it automatically.
However, a different version of webpack was detected higher up in the tree:
  /usr/app/node_modules/webpack (version: 2.7.0)
Manually installing incompatible versions is known to cause hard-to-debug issues.
If you would prefer to ignore this check, add SKIP_PREFLIGHT_CHECK=true to an .env file in your project.
That will permanently disable this message but you might encounter other issues.
To fix the dependency tree, try following the steps below in the exact order:
  1. Delete package-lock.json (not package.json!) and/or yarn.lock in your project folder.
  2. Delete node_modules in your project folder.
  3. Remove "webpack" from dependencies and/or devDependencies in the package.json file in your project folder.
  4. Run npm install or yarn, depending on the package manager you use.
In most cases, this should be enough to fix the problem.
If this has not helped, there are a few other things you can try:
  5. If you used npm, install yarn (http://yarnpkg.com/) and repeat the above steps with it instead.
     This may help because npm has known issues with package hoisting which may get resolved in future versions.
  6. Check if /usr/app/node_modules/webpack is outside your project directory.
     For example, you might have accidentally installed something in your home folder.
  7. Try running npm ls webpack in your project folder.
     This will tell you which other package (apart from the expected react-scripts) installed webpack.
If nothing else helps, add SKIP_PREFLIGHT_CHECK=true to an .env file in your project.
That would permanently disable this preflight check in case you want to proceed anyway.
P.S. We know this message is long but please read the steps above :-) We hope you find them helpful!
npm ERR! code ELIFECYCLE
npm ERR! errno 1
npm ERR! frontendreceitas@0.1.0 start: `react-scripts start`
npm ERR! Exit status 1
npm ERR!
npm ERR! Failed at the frontendreceitas@0.1.0 start script.
npm ERR! This is probably not a problem with npm. There is likely additional logging output above.
npm ERR! A complete log of this run can be found in:
npm ERR!     /root/.npm/_logs/2020-01-16T12_18_37_835Z-debug.log
```


## Referencias 
Deployment does not have minimum availability #14013 - https://github.com/rancher/rancher/issues/14013
