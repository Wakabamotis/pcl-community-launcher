# PCL Community Launcher

An open-source, non-commercial third-party launcher for Minecraft: Java Edition.

> **Unofficial project**
> PCL Community Launcher is an independent community project. It is not
> affiliated with, endorsed by, or sponsored by the official Plain Craft
> Launcher (PCL) team, Mojang Studios, or Microsoft. Minecraft is a trademark
> of Mojang Synergies AB.

## Overview

PCL Community Launcher is a Windows desktop launcher for Minecraft: Java
Edition. It aims to make installing and launching Minecraft, mod loaders, and
community content simple, while using Microsoft's official OAuth 2.0
authentication flow for genuine accounts.

The project is currently in development. Features, download sources, and user
interfaces may change between builds.

## Status

This repository contains the public project documentation for the AppID
review. The source code will be published when the first public build is
ready.

## Features

Planned and current features:

- Microsoft account sign-in using the official OAuth 2.0 device code flow
- Xbox Live and XSTS authentication
- Minecraft ownership verification through Minecraft Services
- Minecraft version installation, repair, and instance isolation
- Forge, NeoForge, Fabric, OptiFine, and LiteLoader installation
- Mod, resource pack, shader pack, and modpack installation
- Java runtime detection and management
- Crash log analysis and diagnostic reports

Some features are still under development. See the issue tracker for the
current status.

## Authentication and ownership verification

PCL Community Launcher never asks for your Microsoft password. Sign-in happens
on Microsoft's own website using the device code flow.

The launcher uses the following services:

| Service | Endpoint | Purpose |
| --- | --- | --- |
| Microsoft OAuth 2.0 | `login.microsoftonline.com/consumers/oauth2/v2.0/devicecode` | Start device code sign-in |
| Microsoft OAuth 2.0 | `login.microsoftonline.com/consumers/oauth2/v2.0/token` | Exchange device code / refresh token |
| Xbox Live | `user.auth.xboxlive.com/user/authenticate` | Obtain Xbox Live token |
| XSTS | `xsts.auth.xboxlive.com/xsts/authorize` | Obtain XSTS token |
| Minecraft Services | `api.minecraftservices.com/authentication/login_with_xbox` | Obtain Minecraft access token |
| Minecraft Services | `api.minecraftservices.com/entitlements/mcstore` | Verify game ownership |
| Minecraft Services | `api.minecraftservices.com/minecraft/profile` | Read Minecraft profile |

The launcher verifies game ownership before enabling the authenticated launch
flow. It does not bypass or disable authentication, ownership checks, license
checks, or other safety features. Accounts without a valid Minecraft
entitlement are blocked from the authenticated launch flow.

## Security

- Never enter your Microsoft password into the launcher or any third-party
  website claiming to be the launcher.
- The launcher does not ask for your password and does not store it.
- Authentication tokens are stored locally on your device.
- Report security issues privately to <CONTACT_EMAIL>.

## Privacy

See [PRIVACY.md](PRIVACY.md) for the full privacy policy.

In short:

- Microsoft refresh tokens are stored locally on your device.
- The launcher does not operate an account server and does not receive your
  Microsoft password.
- We do not sell or rent personal information.
- The launcher communicates directly with Microsoft, Xbox Live, and Minecraft
  Services for authentication.

## Download

The project is not yet publicly released. Release artifacts will be published
when the first public build is ready.

## Contributing

Contributions are welcome. Please open an issue before starting a large change,
and follow the existing code style.

## License and attribution

This project is based on the open-source Plain Craft Launcher (PCL) project.
PCL is copyright (c) 龙腾猫跃 (LTCat) and contributors. See [LICENCE](LICENCE)
for the PCL license terms. If you redistribute this project, you must comply
with the PCL license, including its attribution and naming requirements.

If this repository does not contain PCL-derived code, replace this section with
your own license.

## Contact

- Email: ren752575@gmail.com
- Issues: https://github.com/Wakabamotis/pcl-community-launcher/issues

## Disclaimer

Minecraft is a trademark of Mojang Synergies AB. PCL Community Launcher is not
affiliated with Mojang Studios, Microsoft, or the official PCL team. All game
assets and services remain the property of their respective owners.
