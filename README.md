# the ENA website code is fully based on the CTP website: [https://github.com/AmericanRedCross/ctp-website/blob/gh-pages/_includes/toolkit.html#L426](https://github.com/AmericanRedCross/ctp-website/blob/gh-pages/_includes/toolkit.html#L426)

# ena-website

The Dropbox folder hierarchy needs to be as follows:

- Emergency Needs Assessment Toolkit Final
  - en / es / etc. (ISO 639-1 two-letter language code)
    - 1. Essential *(folder name must match this exactly)*
      - *(overview toolkit docs go here outside of any subfolders)*
      - *(a zip of the entire toolkit should be saved here outside of any subfolders)*
      - folders for sections and documents can be named anything but should sort into the order you want them to display
      - 1 - Guidelines
      - 2 - APE templates
      - 3 ENA Team Deployments
      - 4 - APE Training & Workshop Content
      - 5 - Job Descriptions
    - 2. Additional *(folder name must match this exactly)*
      - 1 - Guidelines *(the words should be translated but the number 1 must be included)*
      - 2 - APE Templates *(the words should be translated but the number 2 must be included)*
      - 3 - ENA team Deployments
      - 4 - APE Training & Workshop Content
      - 5 - Others

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
