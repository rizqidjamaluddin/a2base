Setup:

```
npm install
npm start
```

To build `dist` folder for deployment: 

```
npm build
```

On Vagrant/Homestead?

Tweak `package.json`:

```
"start": "webpack-dev-server --inline --progress --port 8080 --host 0.0.0.0",
```

Tweak `config/webpack.dev.js`, add this block in the config object: 

```
watchOptions: {
    poll: true
}
```

And add port forwarding on port 8080 guest.
