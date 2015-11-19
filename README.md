# vagrant-php-template
A basic vagrant template for PHP development (apache2)

### Installation
1. Clone this repository or download the [Vagrantfile](Vagrantfile).
2. `vagrant up` to create/start the vm.

That's it.

### Development
Put all your web apps source code into the root directory (relative to `Vagrantfile`) and they will be served at `http://localhost:8080`.

### Configuration
- basic ubuntu/trusty64 server with 256mb memory
- apache2 server with `rewrite` and `headers` mod
- web app served at port `8080`
