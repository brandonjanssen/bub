---
title: "Crypto Portfolio Tracker and Price Chart"
date: 2022-10-29T17:22:27+08:00
tags: ["Crypto", "Crypto Portfolio Tracker","Price Charts","Crypto Tools","Wallet Tracking"]
categories: ["Crypto","Crypto Tools","Price Chart"]
cover:
    image: "https://imgur.com/onGr1wx.png" # image path/url
   # alt: "Tetu" # alt text
    #caption: "Fusion operates on the NovaNetwork and Fantom Network" # display caption under cover
    #relative: false # when using page bundles set this to true
    hidden: false # on
---
# Cointop [#](https://cointop.sh/cli/)
-  [Cointop website version ](https://cointop.sh/)
- Cointop docs can be found [here](https://docs.cointop.sh/) which gives a wealth of info on how to configure and customize cointop.
  
---
## How to install
There is multiple ways to install cointop depending on the platform you’re on.
- From source (always latest and recommended) [#](https://docs.cointop.sh/install/#from-source-always-latest-and-recommended)
	- Make sure to have [go](https://golang.org/) (1.17+) installed, then do:
```
go install github.com/cointop-sh/cointop@latest
```
Make sure $GOPATH/bin is added to the $PATH variable if not already.

Now you can run cointop:
```
cointop
```
Download the binary from the[releases](https://github.com/cointop-sh/cointop/releases) page.
```
curl -o- https://raw.githubusercontent.com/cointop-sh/cointop/master/install.sh | bash
```
```
wget -qO- https://raw.githubusercontent.com/cointop-sh/cointop/master/install.sh | bash
```
Homebrew (macOS) [#](https://docs.cointop.sh/install/#homebrew-macos)
cointop is available via [Homebrew](https://formulae.brew.sh/formula/cointop) for macOS:
```
brew install cointop
```
Run
```
cointop
```
Snap (Ubuntu) [#](https://docs.cointop.sh/install/#snap-ubuntu)
cointop is available as a [snap](https://snapcraft.io/cointop) for Linux users.
```bash
sudo snap install cointop --stable
```
Snaps:
```
sudo snap run cointop
```
Note: snaps don’t work in Windows WSL. See this [issue thread.](https://forum.snapcraft.io/t/windows-subsystem-for-linux/216)

Copr (Fedora) [#](https://docs.cointop.sh/install/#copr-fedora)
cointop is available as a [copr](https://copr.fedorainfracloud.org/coprs/miguelmota/cointop/) package.

First, enable the repository
```
sudo dnf copr enable miguelmota/cointop -y
```
Install cointop
```
sudo dnf install cointop
```
Run
```
cointop
```
AUR [#](https://docs.cointop.sh/install/#aur-arch-linux)
cointop is available as an [AUR](https://aur.archlinux.org/packages/cointop) package.
```
git clone https://aur.archlinux.org/cointop.git
cd cointop
makepkg -si
```
Using [yay](https://github.com/Jguer/yay)
```
yay -S cointop
```
XBPS (Void Linux) [#](https://docs.cointop.sh/install/#xbps-void-linux)
cointop is available as a [XBPS](https://voidlinux.org/packages/) package.
```
sudo xbps-install -S cointop
```
Flatpak (Linux) [#](https://docs.cointop.sh/install/#flatpak-linux)
cointop is available as a [Flatpak](https://flatpak.org/) package via the [Flathub](https://flathub.org/apps/details/com.github.miguelmota.Cointop) registry.

Add the flathub repository (if not done so already)
```
sudo flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
```
Install cointop flatpak
```
sudo flatpak install flathub com.github.miguelmota.Cointop
```
Run cointop flatpak

flatpak run com.github.miguelmota.Cointop
NixOS (Linux) [#](https://docs.cointop.sh/install/#nixos-linux)
cointop is available as a [nixpkg.](https://search.nixos.org/packages?channel=unstable&show=cointop&from=0&size=30&sort=relevance&query=cointop)
```
nix-env -iA nixpkgs.cointop
```
AppImage (Linux) [#](https://docs.cointop.sh/install/#appimage-linux)
You can download the AppImage from the [releases](https://github.com/cointop-sh/cointop/releases) page.
```
VERSION=$(curl --silent "https://api.github.com/repos/cointop-sh/cointop/releases/latest" | grep -Po --color=never '"tag_name": ".\K.*?(?=")')
URL="https://github.com/cointop-sh/cointop/releases/download/v$VERSION/cointop-v$VERSION.glibc2.32-x86_64.AppImage"
wget $URL
```
Must make AppImage executable:
```
chmod +x cointop-*.AppImage
```
Run AppImage:
```
./cointop-*.AppImage
```
FreshPorts (FreeBSD / OpenBSD) [#](https://docs.cointop.sh/install/#freshports-freebsd--openbsd)
cointop is available as a [FreshPort](https://www.freshports.org/finance/cointop/) package.

sudo pkg install cointop
Windows (PowerShell / WSL) [#](https://docs.cointop.sh/install/#windows-powershell--wsl)
Install [Go](https://golang.org/doc/install) and [git](https://git-scm.com/download/win), then:
```
go get -u github.com/cointop-sh/cointop
```
You’ll need additional font support for Windows. Please see the [wiki](https://github.com/cointop-sh/cointop/wiki/Windows-Command-Prompt-and-WSL-Font-Support) for instructions.

Docker [#](https://docs.cointop.sh/install/#docker)
cointop is available on [Docker Hub.](https://hub.docker.com/r/cointop/cointop)
```
docker run -it cointop/cointop
```
Note: the config is under /root/.config/cointop in container, so attach a volume to make it persistent in host:
```
docker run -v ~/.cache/cointop:/root/.config/cointop -it cointop/cointop
```
Binaries [#](https://docs.cointop.sh/install/#binaries)
You can find pre-built binaries on the [releases](https://github.com/cointop-sh/cointop/releases) page.


  
  
  
  The first time you run cointop, it’ll create a config file in:

```bash
~/.config/cointop/config.toml
```
## Increase coin search results
There is a limit on the number of coins that cointop fetches by default. You can increase this by passing `--max-pages` and `--per-page` arguments on the command line. Like this
` /home/dmne/go/bin/cointop --max-pages 500`

## List of currencies for conversion  
`AUD`, `BRL`, `CAD`, `CFH`, `CLP`, `CNY`, `CZK`, `DKK`, `EUR`, `GBP`, `HKD`, `HUF`, `IDR`, `ILS`, `INR`, `JPY`, `KRW`, `MXN`, `MYR`, `NOK`, `NZD`, `PLN`, `PHP`, `PKR`, `RUB`, `SEK`, `SGD`, `THB`, `TRY`, `TWD`, `USD`, `VND`, and `ZAR`.

Run this in your terminal `cointop price` followed buy examples showed below. A small script would be useful if you only want to see exactly what you are looking for.

```bash
$ cointop price --coin ethereum
$277.76

$ cointop price -c ethereum --currency btc
Ƀ0.02814

$ cointop -c ethereum -f eur
€245.51

$ cointop price -c ethereum -f usd --api coinmarketcap
$276.37
```
## Holdings View
Each coin consists of four values: coin name, coin amount, cost-price, cost-currency.

For example, the following configuration includes 100 ALGO at USD1.95 each; and 0.1 BTC at AUD50100.83 each.

```toml
 holdings = [["Algorand", "100", "1.95", "USD"], ["Bitcoin", "0.1", "50100.83", "AUD"]]
```

With this configuration, four new columns are useful:

-   `cost_price` the price and currency that the coins were purchased at
-   `cost` the cost (in the current currency) of the coins
-   `pnl` the PNL of the coins (current value vs original cost)
-   `pnl_percent` the PNL of the coins as a fraction of the original cost
---
![](https://imgur.com/qUs79cH.png)

---
## Short cut keys
- There is a lot of keys to remember, im sure once you get things all figured out you wont use all of them. 
	- The ones you do use all the the time are configurable to your liking's.

| Description                                                           | Key                                                                                                                                                                                                                      | Description                  | Key |   
| --------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------------------------- | --- |
| [View Favorites](https://docs.cointop.sh/favorites/#view-favorites)   | F (Shift+f)                                                                                                                                                                                                              | last_page                    | $   |     |     |     |     |     |
| [Exit Favorites](https://docs.cointop.sh/favorites/#exit-favorites)   | F (Shift+f) or q or Esc                                                                                                                                                                                                  | move_to_first_page_first_row | 0   |     |     |     |     |     |
| [Add Favorite](https://docs.cointop.sh/favorites/#add-favorite)       | f or Space                                                                                                                                                                                                               | sort_column_1h_change        | 1   |     |     |     |     |     |
| [Remove Favorite](https://docs.cointop.sh/favorites/#remove-favorite) | f or Space                                                                                                                                                                                                               | sort_column_24h_change       | 2   |     |     |     |     |     |
| [View Portfolio ](https://docs.cointop.sh/portfolio/#view-portfolio)  | P (Shift+p)                                                                                                                                                                                                              | sort_column_7d_change        | 7   |     |     |     |     |     |
| [Exit Portfolio](https://docs.cointop.sh/portfolio/#exit-portfolio)   | P (Shift+p)  or q or Esc                                                                                                                                                                                                 | help                         | ?   |     |     |     |     |     |
| [Add Entry](https://docs.cointop.sh/portfolio/#add-entry)             | press `e` on the highlighted coin,enter new value and press `Enter`                                                                                                                                                      | toggle_table_fullscreen      | \   |     |     |     |     |     |
| [Edit Entry ](https://docs.cointop.sh/portfolio/#edit-entry)          | press `e` on the highlighted coin,enter new value and press `Enter`                                                                                                                                                      | first_chart_range            | {   |     |     |     |     |     |
| [ Remove Entry](https://docs.cointop.sh/portfolio/#remove-entry)      | To remove an entry in your portfolio, `press e` on the highlighted coin and set the value to an empty value and `press Enter`                                                                                            | last_chart_range             | }   |     |     |     |     |     |
| [Changing Chart](https://docs.cointop.sh/portfolio/#changing-chart)   | To change  the coin for the chart, `press Enter` on the highlighted coin. Pressing `Enter again` on the same highlighted row will show the global chart again.                                                           | scroll_left                  | <   |     |     |     |     |     |
| [Searching](https://docs.cointop.sh/searching/#searching)             | To search for coins, `press /` to bring up the search prompt. Enter the search query and then hit `Enter` to submit. The coin that matches closes to the query will be highlighted.Press `Esc` to exit the search prompt | scroll_right                 | >   |     |     |     |     |     |
| [Chart View](https://docs.cointop.sh/chart/#chart)                    | The default chart shown is the global market cap of all cryptocurrencies.Press `Enter` to toggle the price chart for the highlighted coin.                                                                               | search                       | /   |     |     |     |     |     |
| [Date Ranges ](https://docs.cointop.sh/chart/#date-ranges)            | Press`]` to cycle to the next date range.Press `[` to cycle to the previous date range.Press `{`to select the first date range.Press `}` to selected the last date range.                                                | next_chart_range             | ]   |     |     |     |     |     |
| [Chart Size](https://docs.cointop.sh/chart/#size)                     | Press `Ctrl+j` to increase the chart height.Press `Ctrl+k` to decrease the chart height.                                                                                                                                 | previous_chart_range         | [   |     |     |     |     |     |


You can configure each key in `~/.config/cointop/config.toml`



| Key      | Description                   | Key       | Description                     |    
| -------- | ----------------------------- | --------- | ------------------------------- | 
| C        | show_currency_convert_menu    | E         | show_portfolio_edit_menu        |    
| G        | move_to_page_last_row         | H         | move_to_page_visible_first_row  |    
| L        | move_to_page_visible_last_row | M         | move_to_page_visible_middle_row |    
| O        | open_link                     | P         | toggle_portfolio                |    
| a        | sort_column_available_supply  | alt+down  | sort_column_desc                |    
| alt+left | sort_left_column              | alt+right | sort_right_column               |    
| alt+up   | sort_column_asc               | down      | move_down                       |    
| left     | previous_page                 | right     | next_page                       |    
| up       | move_up                       | c         | show_currency_convert_menu      |    
| b        | sort_column_balance           | ctrl+c    | quit                            |    
| ctrl+d   | page_down                     | ctrl+f    | open_search                     |    
| ctrl+j   | enlarge_chart                 | ctrl+k    | shorten_chart                   |    
| ctrl+n   | next_page                     | e         | show_portfolio_edit_menu        |    
| ctrl+p   | previous_page                 | end       | move_to_page_last_row           |    
| ctrl+r   | refresh                       | enter     | toggle_row_chart                |    
| ctrl+s   | save                          | esc       | quit                            |    
| ctrl+u   | page_up                       | f         | toggle_favorite                 |    
| pagedown | page_down                     | F         | toggle_show_favorites           |    
| pageup   | page_up                       | F1        | help                            |    
| g        | move_to_page_first_row        | j         | move_down                       |    
| h        | previous_page                 | k         | move_up                         |    
| home     | move_to_page_first_row        | l         | next_page                       |    
| m        | sort_column_market_cap        | q         | quit_view                       |    
| n        | sort_column_name              | Q         | quit_view                       |    
| o        | open_link                     | r         | sort_column_rank                |    
| p        | sort_column_price             | s         | sort_column_symbol              |    
| space    | toggle_favorite               | t         | sort_column_total_supply        |    
| tab      | move_down_or_next_page        | u         | sort_column_last_updated        |    
| v        | sort_column_24h_volume        |           |                                 |    

---
![](https://imgur.com/6NCsf23.png)









