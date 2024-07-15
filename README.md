<h1 align=center>my-warden-install-guide</h1>

<section align=center>
  <img style="align: center;" src="https://pbs.twimg.com/profile_images/1797575442385235969/aY0Qhzjs_200x200.jpg">
</section>

# Install
## Download and Build source code
```
git clone --depth 1 --branch v0.3.0 https://github.com/warden-protocol/wardenprotocol/
just build

build/wardend init <custom_moniker>
```

## Configure
```
cd $HOME/.warden/config
rm genesis.json
wget https://raw.githubusercontent.com/warden-protocol/networks/main/testnets/buenavista/genesis.json
```
```
# Set minimum gas price & peers
sed -i 's/minimum-gas-prices = ""/minimum-gas-prices = "0.0025uward"/' app.toml
sed -i 's/persistent_peers = ""/persistent_peers = "650c66dda5f7aa954f44fd6148a6f32b085ca792@sentry-0.buenavista.wardenprotocol.org:26656,7c70120717ef5eae8236162ede6819249bd6587d@sentry-1.buenavista.wardenprotocol.org:26656,288116b75c3c710268b5d86182d8dd5e33a6b56f@sentry-2.buenavista.wardenprotocol.org:26656"/' config.toml
```
## Start Warden
```
wardend start
```
