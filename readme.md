Setup:

```
npm install
npm start
```

To build `dist` folder for deployment: 

```
npm build
```

## On Vagrant/Homestead?

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

After running `npm start`, if you can't access `localhost:8080` from your browser, [set up port forwarding](https://www.vagrantup.com/docs/networking/forwarded_ports.html) in your vagrantfile:

```
Vagrant.configure("2") do |config|
  config.vm.network "forwarded_port", guest: 8080, host: 8888
end
```

Which would make the site available at `localhost:8888`.
