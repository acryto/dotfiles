# dotfiles
using i3 and urxvt

## ~/.config/i3/config
```
# Change dpi
exec xrandr --dpi 144

# Display Wallpaper
exec_always feh --bg-fill ~/documents/papes/bg.jpg

# Keybinding for i3lock
bindsym $mod+x exec i3lock -i ~/documents/papes/giampaola.png
# a me funzia solo con png

# Window Colors
set $ibgcolor 	#000000
set $bgcolor	#996593
set $textcolor	#ffffff
set $ubgcolor	#99cc00

#			border		background	text		indicator
client.focused 		$bgcolor	$bgcolor	$textcolor	$bgcolor
client.unfocused	$ibgcolor	$ibgcolor	$textcolor	$ibgcolor
client.focused_inactive	$ibgcolor	$ibgcolor	$textcolor	$ibgcolor
client.urgent		$ubgcolor	$ubgcolor	$textcolor	$ubgcolor

# No borderp
for_window [class="^.*"] border pixel 1

# Change brightness
bindsym XF86MonBrightnessUp exec light -A 5;
bindsym XF86MonBrightnessDown exec light -U 5;
```

## ~/.config/i3status/i3status.conf
```
general {
        colors = true
        interval = 5
}

#order += "ipv6"
#order += "wireless _first_"
#order += "ethernet _first_"
order += "battery all"
#order += "disk /"
#order += "load"
#order += "memory"

order += "tztime local"

wireless _first_ {
        format_up = "W: (%quality at %essid) %ip"
        format_down = "W: down"
}

ethernet _first_ {
        format_up = "E: %ip (%speed)"
        format_down = "E: down"
}

battery all {
        format = "%status %percentage %remaining"
}

disk "/" {
        format = "%avail"
}

load {
        format = "%1min"
}

memory {
        format = "%used | %available"
        threshold_degraded = "1G"
        format_degraded = "MEMORY < %available"
}


tztime local {
        format = "%Y-%m-%d %H:%M"
}
```

## ~/.Xresources
```
URxvt.transparent:true
URxvt.shading:20
URxvt.scrollBar: false

Xft.dpi: 144
*.font: xft:DejaVu Sans Mono:size=8

! special
*.foreground: #c2c2b0
*.background: #202020
*.cursorColor: #c2c2b0

!black
*.color0: #151515
*.color8: #3f3639

!red
*.color1: #b44242
*.color9: #dc7671

!green
*.color2: #95a328
*.color10: #e8e85a


! yellow:
*.color3: #e1c135
*.color11: #9e9052

! blue:
*.color4: #60928f
*.color12: #76c39b

! magenta
*.color5: #7c435a
*.color13: #86596c

! cyan
*.color6: #a48b4a
*.color14: #ceb34f

! white
*.color7: #c2c2b0
*.color15: #b0afa8
```
