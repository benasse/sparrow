+++
# Hero widget.
widget = "hero"  # See https://sourcethemes.com/academic/docs/page-builder/
headless = true  # This file represents a page section.
active = true  # Activate this widget? true/false
weight = 10  # Order that this section will appear.

title = "Sparrow Builds"

# Hero image (optional). Enter filename of an image in the `static/img/` folder.
#hero_media = "hero-academic.png"

[design.background]
  # Apply a background color, gradient, or image.
  #   Uncomment (by removing `#`) an option to apply it.
  #   Choose a light or dark text color by setting `text_color_light`.
  #   Any HTML color name or Hex value is valid.

  # Background color.
  # color = "navy"
  
  # Background gradient.
  #gradient_start = "#4bb4e3"
  #gradient_end = "#2b94c3"
  
  # Background image.
  # image = ""  # Name of image in `static/img/`.
  # image_darken = 0.6  # Darken the image? Range 0-1 where 0 is transparent and 1 is opaque.
  # image_size = "cover"  #  Options are `cover` (default), `contain`, or `actual` size.
  # image_position = "center"  # Options include `left`, `center` (default), or `right`.
  # image_parallax = true  # Use a fun parallax-like fixed background effect? true/false
  
  # Text color (true=light or false=dark).
  text_color_light = false

# Call to action links (optional).
#   Display link(s) by specifying a URL and label below. Icon is optional for `[cta]`.
#   Remove a link/note by deleting a cta/note block.
[cta]
  url = "/docs"
  label = "View documentation"
  icon_pack = "fas"
  icon = "download"
  
#[cta_alt]
#  url = "https://sourcethemes.com/academic/"
#  label = "View documentation"

# Note. An optional note to show underneath the links.
#[cta_note]
#  label = '<a class="js-github-release" href="https://sourcethemes.com/academic/updates" data-repo="gcushen/hugo-academic">Latest release<!-- V --></a>'
+++
Sparrow is an unofficial build for armhf architecture of the awesome <a href="https://wazo-platform.org\" target="_blank" >Wazo Platform</a>.
It allows you to host complete Open Source, and programable telephone system on a <a href="https://www.raspberrypi.org/" target="_blank" >Raspberry Pi</a>.
{{% alert note %}}
<div class="message focus" data-component="message">
<a href="https://wazo-platform.org/" >Wazo Platform</a> is an Open Source project writen in <a href="https://www.python.org" target="_blank">python</a> who gets the best from <a href="https://www.asterisk.org" target="_blank">asterisk</a> and <a href="https://kamailio.org/" target="_blank">kamailio</a> to build a telecom platform.
{{% /alert %}}
