# IP Calculator

A browser-based **IPv4 subnet calculator**. Enter an IP address and a CIDR prefix, and it shows the subnet mask, network and broadcast addresses, the usable host range and the address class, in both dotted-decimal and binary.

**Live demo:** https://rexhinokovaci.github.io/IPCalculator/

## Features

Input: four octets (`0–255`) plus a CIDR prefix length (`/0–/32`), validated before calculating.

| Output | Example for `192.168.1.1/26` |
| --- | --- |
| Subnet mask | `255.255.255.192` |
| Network address | `192.168.1.0` |
| Broadcast address | `192.168.1.63` |
| Usable host range | `192.168.1.1 – 192.168.1.62` |
| Standard class | `C` (also detects loopback, multicast class D and experimental class E) |
| Binary IP / mask / network / broadcast | e.g. mask `11111111.11111111.11111111.11000000` |

The calculation runs entirely on the client: it converts each octet to 8-bit binary, builds the mask from the prefix length, and ANDs/ORs the boundary octet to get the network and broadcast addresses.

The page also includes a light/dark mode toggle and a responsive Bootstrap layout.

## Tech stack

- HTML5, CSS3 (Sass source in `sass/`), vanilla JavaScript for the calculator (`script.js`)
- Bootstrap 4, jQuery 3.3, Headroom.js, Owl Carousel, Unicons
- Hosted on GitHub Pages

## Running locally

No build step needed. Open `index.html` in a browser or serve the folder:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Project structure

```
index.html            # page layout and calculator form
script.js             # subnet calculation logic
css/, sass/           # Bootstrap, plugins and site theme
js/                   # jQuery, Bootstrap, Headroom, Owl Carousel, smooth scroll, dark mode toggle
font/, images/        # icon font and illustrations
```

## Related

- [NetworksWeb](https://github.com/rexhinokovaci/NetworksWeb): hub site that links this calculator and the IP tracker
- [IPaddress-tracker](https://github.com/rexhinokovaci/IPaddress-tracker): look up the location of any public IP

---

Built by [Rexhino Kovaci](https://github.com/rexhinokovaci) — DevOps & AI engineer in Tirana, Albania. Need an app built? [Get in touch](mailto:kovacirexhino@gmail.com).
