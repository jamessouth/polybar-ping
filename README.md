<h1 align="center">polybar-keyd</h1>

<p>&nbsp;</p>

A ping module for your

<div align="center">
	<picture>
 	 <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/polybar/polybar/master/doc/_static/banner-dark-mode.png">
 	 <img alt="polybar logo" src="https://raw.githubusercontent.com/polybar/polybar/master/doc/_static/banner.png">
	</picture>
</div>

<p>&nbsp;</p>

<p align="center">
	<a href="https://github.com/jamessouth/polybar-keyd/blob/master/LICENSE"><img src="https://img.shields.io/github/license/jamessouth/polybar-keyd"></a>
	<a href="https://archlinux.org/"><img src="https://img.shields.io/badge/Linux-d.svg?logoWidth=40&labelColor=d35e49&color=E3C567&logoColor=000000&logo=Linux"></a>
	<a href="https://www.gnu.org/software/bash/manual/"><img src="https://img.shields.io/badge/Bash-d.svg?logoWidth=40&labelColor=4eaa25&color=293137&logoColor=ffffff&logo=GNU%20Bash"></a>
	<img src="https://img.shields.io/badge/awesome-%C6%94%F0%9D%9A%BA%C5%9E-darkred.svg">
</p>

<p>&nbsp;</p>

## Description
This module calls a simple one-time `ping` command to check network connectivity. It prints an up arrow if successful and a down arrow if not. It uses [IPC](https://github.com/polybar/polybar/wiki/Module:-ipc), so it isn't continually pinging away; just click it when you want to see if you're down or back up.

<p>&nbsp;</p>

## Dependencies
None

<p>&nbsp;</p>

## Configuration
None

<p>&nbsp;</p>

## Module
```ini
[module/ping]
type = custom/ipc

hook-0 = ping -c 1 -W 2 8.8.8.8 >/dev/null 2>&1 && printf "↑\n" || printf "↓\n"
click-left = "#ping.hook.0"
initial = 1

;your formatting here, e.g.:
format-foreground = ${colors.orange}
format-prefix = "%{T1}png "
label = %{T3}%output%
```

The module sends one packet to the server, waits no more than two seconds for a response, consumes any output, and reports success or failure.

<p>&nbsp;</p>

## My other polybar modules
Please check out:
  * [polybar-time-bar](https://github.com/jamessouth/polybar-time-bar)
  * [polybar-nightlight](https://github.com/jamessouth/polybar-nightlight)
  * [polybar-binary-clock-fonts](https://github.com/jamessouth/polybar-binary-clock-fonts)

<p>&nbsp;</p>
