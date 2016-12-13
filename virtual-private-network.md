```sh
pptsetup --create nuupxe --server ... --username ... --password ... --encrypt
```

```sh
pon nuupxe debug dump lgfd 2 nodetach
```

```sh
route
```

```sh
route del default wlan4
```

```sh
route add -host 192.,167.1.253 dev ppp0
```

```sh
route add default dev nuupxe
```

```sh
route add default dev wlan4
```

```sh
route add default dev ppp0
```

```sh
route
```