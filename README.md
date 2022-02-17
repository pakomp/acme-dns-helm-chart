# Helm chart for acme-dns
A Helm chart for ACME-DNS

Repository ACME-DNS: https://github.com/joohoi/acme-dns


It's the minimal helm chart for deploy acme-dns in kubernetes cluster

Helm chart will deploy statefullset acme-dns with example config.cfg from acme-dns repo. 

If needed change config.cfg, your can set param of predeploy command helm.
# Usage

```
git clone https://github.com/obsessionsys/acme-dns-helm-chart
helm upgrade --install -n default acme-dns ./chart
```

# How to deploy acme-dns with config.cfg

Prepare your configuration file (config.cfg)  with the necessary parameters before deployment and run the command

```
helm install -n default acme-dns --set configFile=/path-to-config/config.cfg ./chart
```

If you don't want to prepare a configuration file, you can pass the necessary parameters via --set command in section appConfiguration

```
helm install -n default acme-dns \
  --set appConfiguration.listenInterface=0.0.0.0:53
  --set appConfiguration.domain=auth.domain.com \
  --set appConfiguration.nsname=auth.domain.com \
  --set appConfiguration.nsadmin=admin.domain.com \
  --set appConfiguration.publicIP=1.1.1.1 \
  ./chart
```
