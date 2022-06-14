### **Typo**


# [h1] The largest heading
## [h2] heading
### [h3] heading
#### [h4] heading
##### [h5] heading
###### [h6] The smallest heading

----- 

### Bold

**This is bold text**

----- 

### Italic

*This text is italicized*	

----- 
### Strikethrough

~~This was mistaken text~~	

----- 
### Bold and nested italic

**This text is _extremely_ important**	

----- 
### All bold and italic	

***All this text is important***	

----- 
### Subscript	

<sub>This is a subscript text</sub>	

----- 
### Superscript

<sup>This is a superscript text</sup>	

----- 
### Quote

Text that is not a quote

> Text that is a quote
> Text that is a quote
> Text that is a quote

----- 
### Quoting code

Use `git status` to list all new or modified files that haven't yet been committed.


Some basic Git commands are:
```
git status
git add
git commit
```

```docker
# image
FROM php:7.1-apache

# envs
ENV INSTALL_DIR /var/www/html

# install composer
RUN curl -sS https://getcomposer.org/installer | php \
&& mv composer.phar /usr/local/bin/composer

# install libraries
RUN requirements="cron libpng-dev libmcrypt-dev libmcrypt4 libcurl3-dev libfreetype6 libjpeg62-turbo libjpeg62-turbo-dev libfreetype6-dev libicu-dev libxslt1-dev" \
 && apt-get update \
 && apt-get install -y $requirements \
 && rm -rf /var/lib/apt/lists/* \
 && docker-php-ext-install pdo_mysql \
 && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
 && docker-php-ext-install gd \
 && docker-php-ext-install mcrypt \
 && docker-php-ext-install mbstring \
 && docker-php-ext-install zip \
 && docker-php-ext-install intl \
 && docker-php-ext-install xsl \
 && docker-php-ext-install soap \
 && docker-php-ext-install bcmath

# add magento cron job
COPY ./crontab /etc/cron.d/magento2-cron
RUN chmod 0644 /etc/cron.d/magento2-cron
RUN crontab -u www-data /etc/cron.d/magento2-cron

# turn on mod_rewrite
RUN a2enmod rewrite

# set memory limits
RUN echo "memory_limit=2048M" > /usr/local/etc/php/conf.d/memory-limit.ini

# clean apt-get
RUN apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

# www-data should own /var/www
RUN chown -R www-data:www-data /var/www

# switch user to www-data
USER www-data

# copy sources with proper user
COPY --chown=www-data . $INSTALL_DIR

# set working dir
WORKDIR $INSTALL_DIR

# composer install
RUN composer install
RUN composer config repositories.magento composer https://repo.magento.com/

# chmod directories
RUN chmod u+x bin/magento

# switch back
USER root

# run cron alongside apache
CMD [ "sh", "-c", "cron && apache2-foreground" ]
```

----- 
### Links

This site was built using [GitHub Pages](https://pages.github.com/).

----- 
### Section links


[Contribution guidelines for this project](docs/CONTRIBUTING.md)

----- 
### Image

![This is an image](https://buddy.works/assets/svg/brands/buddy.svg)

----- 
### Specifying the theme an image is shown to

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://user-images.githubusercontent.com/25423296/163456776-7f95b81a-f1ed-45f7-b7ab-8fa810d529fa.png">
  <source media="(prefers-color-scheme: light)" srcset="https://user-images.githubusercontent.com/25423296/163456779-a8556205-d0a5-45e2-ac17-42d089e3c3f8.png">
  <img alt="Shows an illustrated sun in light color mode and a moon with stars in dark color mode." src="https://user-images.githubusercontent.com/25423296/163456779-a8556205-d0a5-45e2-ac17-42d089e3c3f8.png">
</picture>


----- 
### List 

### Normal list

- George Washington
- John Adams
- Thomas Jefferson

### Order list

1. James Madison
2. James Monroe
3. John Quincy Adams


### Nested Lists

1. First list item
   - First nested list item
     - list item
     - list item
   - Second nested list item
     - list item
     - list item
2. Second list item
   - list item
   - list item
      - list item

----- 
### Task lists

- [x] #739
- [ ] https://github.com/octo-org/octo-repo/issues/740
- [ ] Add delight to the experience when all tasks are complete :tada:
- [ ] \(Optional) Open a followup issue

@github/support What do you think about these updates?

----- 
### emoji

@octocat :+1: This PR looks great - it's ready to merge! :shipit:

----- 
### Footnotes

Here is a simple footnote[^1].

A footnote can also have multiple lines[^2].  

You can also use words, to fit your writing style more closely[^note].

[^1]: My reference.
[^2]: Every new line should be prefixed with 2 spaces.  
  This allows you to have a footnote with multiple lines.
[^note]:
    Named footnotes will still render with numbers instead of the text but allow easier identification and linking.  
    This footnote also has been made with a different syntax using 4 spaces for new lines.
    
----- 
### Hiding content with comments

<!-- This content will not appear in the rendered Markdown -->

----- 
### Ignoring Markdown formatting

Let's rename \*our-new-project\* to \*our-old-project\*.

----- 
### Table

| Left-aligned | Center-aligned | Right-aligned |
| :---         |     :---:      |          ---: |
| git status   | git status     | git status    |
| git diff     | git diff       | git diff      |


----- 
### Diagrams

Here is a simple flow chart:

```mermaid
graph TD;
    A-->B;
    A-->C;
    B-->D;
    C-->D;
```
