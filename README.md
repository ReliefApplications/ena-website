This ENA website is based on the [CTP website]([https://github.com/AmericanRedCross/ctp-website/blob/gh-pages/_includes/toolkit.html#L426](https://github.com/AmericanRedCross/ctp-website/blob/gh-pages/_includes/toolkit.html#L426). 

# ctp-website

### Dropbox structure

For the [document API](https://github.com/AmericanRedCross/ena-website-api) to work the Dropbox folder hierarchy needs to be as follows:

- TODO: add folder structure

### Adding Language support
The site is configured to support 2-letter core language codes. So english is 'en' not 'en-US' and/or 'en-GB'. Using a longer code will not function.

1. tell app config the language exists
  1. add 2-letter language code to ```authorized_locales``` array in \_config.yml
2. include locale file (to support date/time localization)
  1. several already in place (in \_locales dir), otherwise get from [here](https://github.com/svenfuchs/rails-i18n/tree/master/rails/locale)
3. include \_data/```2-letter code```.yml to support site content translations
  1. copy \_data/en.yml, then update text values
  2. note that the url for the nav items can be updates for your language. this needs to align with the permalink in the page frontmatter (see item 4.2 below)
4. create folder of page templates
  1. copy 'en' dir, rename copy as your 2-letter language code
  2. in frontmatter for all templates there within, you need to add the language code and pagename to the ```permalink``` (i.e. /toolkit/ becomes /fr/boite-a-outils/ for the french translation)
