# docker-wordpress-test

* The goal is to run Wordpress as Headless CMS (backend) and use Nuxt as frontend.
* To make things more manageable, we use Docker to containerize the backend (Wordpress), frontend (Nuxt) and database (MySQL).


## Inspiration 

* Wordpress is one of the most popular CMS systems in the world
* But personally, I hate developing anything for it. The API is a convoluted mess.
* So the idea is to run Wordpress as Headless CMS, so the backend (content management) is separated from the frontend (presentation).
* Wordpress offers a REST API, so we can use any frontend technology that can consume that API.
* In this case I opted for Nuxt, because I like the opinionated approach with Vue components and the project structure.
* The project structure itself is based on "Hands-on Nuxt.js Web Development" (see [Appendix](#appendix)).
* Also I wanted to learn about Docker, because installing development servers and databases always was such a hassle in the past.


## Technologies

### Wordpress (Backend)

* Admin user
  * Name: `admin`
  * Password: `password`
* We use https://wpackagist.org/ to load wordpress plugins and themes as composer packages.
* So to make sure to run `cd wordpress && composer install` first, before building composer images.


### Nuxt (Frontend)

* TODO


## Appendix

### Helpful Links

* General
  * [KDE Blog - WordPress REST API as a Back-end with React and Docker (Part 1)](https://kde.design/wordpress-rest-api-as-a-backend-with-react-and-docker-part-1)
  * [KDE Blog - WordPress REST API as a Back-end with React and Docker (Part 2)](https://kde.design/wordpress-rest-api-as-a-backend-with-react-and-docker-part-2)
  * [Dockerize WordPress with themes, plugins and common configuration - Salman Sohail](https://salzam.com/dockerize-wordpress-with-themes-plugins-and-common-configuration/)
  * [How to Install WordPress on Docker (Windows, macOS and Linux)](https://www.hostinger.com/tutorials/run-docker-wordpress)
* Docker
  * [The `docker-compose.yml` file - Divio Documentation](https://docs.divio.com/en/latest/reference/docker-docker-compose/)
  * [Overview of Docker Compose | Docker Documentation](https://docs.docker.com/compose/)
  * [Dockerfile reference | Docker Documentation](https://docs.docker.com/engine/reference/builder/)
  * [Importance of docker layer in dockerfile - Naiveskill](https://naiveskill.com/docker-layer/)
  * [manpages.ubuntu.com - set](http://manpages.ubuntu.com/manpages/jammy/en/man1/set.1posix.html)
  * https://explainshell.com/
  * [Wordpress image official Dockerfile](https://github.com/docker-library/wordpress/blob/master/latest/php8.1/apache/Dockerfile)
  * [Best practices for writing Dockerfiles | Docker Documentation # Unterstand Build Context](https://docs.docker.com/develop/develop-images/dockerfile_best-practices/#understand-build-context)
  * [Docker: Stop All Containers - Unix Tutorial](https://www.unixtutorial.org/docker-stop-all-containers/)
  * [`docker-compose` specification - Github](https://github.com/compose-spec/compose-spec/blob/master/spec.md)
  * [Docker File vs Docker Compose: What's the Difference? - linuxhandbook.com](https://linuxhandbook.com/docker-file-vs-docker-compose/)
  * [docker hub - Wordpress](https://hub.docker.com/_/wordpress)
* PHP
  * [composer self-update - Stackoverflow](https://stackoverflow.com/a/36787045/how-to-update-composer-in-windows-10)
  * [wpackagist - Github](https://github.com/outlandishideas/wpackagist)
  * https://wpackagist.org/
  * [Advanced Custom Fields – WordPress plugin | WordPress.org](https://wordpress.org/plugins/advanced-custom-fields/)
  * [WordPress 4.8 on Docker REST API Not Accessible - Stackoverflow](https://stackoverflow.com/a/45105113/wordpress-4-8-on-docker-rest-api-not-accessible)
  * [Wordpress versions](https://codex.wordpress.org/WordPress_Versions)
  * [Using the REST API | REST API Handbook | WordPress Developer Resources](https://developer.wordpress.org/rest-api/using-the-rest-api/)
  * [How To Use The WordPress REST API Plugin - wpengine.com](https://wpengine.com/resources/using-wordpress-rest-api-plugin/)
  * [WordPress REST API: What It Is and How to Get Started Using It - codeinwp.com](https://www.codeinwp.com/blog/wordpress-rest-api/)
* Nuxt
  * [Creating a Website with Nuxt.js and WordPress REST API](https://medium.com/@moustachedesign/creating-a-website-with-nuxt-js-and-wordpress-rest-api-51cf66599cf3)
  * [Nuxt + WordPress REST API boilerplate](https://github.com/bovas85/nuxt-headless)


### Hands-on Nuxt.js Web Development

> ## Creating headless REST APIs in WordPress
> 
> WordPress (WordPress.org) is an open source PHP CMS for general-purpose website development. 
> It is not "headless" by default; it is stacked with a template system. 
> This means the view and the data are intertwined. 
> However, since 2015 (WordPress 4.4), the REST API infrastructure has been integrated into WordPress core for developers, and now
> all the default endpoints can be accessed if you append /wp-json/ to your website-based URL. 
> You can also extend the WordPress REST API and add your own custom endpoints. 
> So, we can easily use WordPress as a "headless" REST API by ignoring the view. 
> You will find out how to achieve this in the upcoming sections. 
> 
> To speed up the development process, we will install the following WordPress plugins:
> 
> 1. **Advanced Custom Fields (ACF)** for creating custom meta boxes. 
>    For more information about this plugin, please visit https://www.advancedcustomfields.com/.
> 2. **The ACF Repeater Field** for creating a repeatable set of subfields. 
>    It is an ACF premium add-on (https://www.advancedcustomfields.com/add-ons/).
>    You can purchase it from https://www.advancedcustomfields.com/add-ons/repeater-field/. 
>    Alternatively, you can get it by default from ACF PRO at https://www.advancedcustomfields.com/pro/.
> 3. **Rewrite Rules Inspector** for inspecting and flushing your rewrite rules in WordPress. 
>    For more information about this plugin, please visit https://wordpress.org/plugins/rewrite-rules-inspector/
> 
> You can create your own plugins and meta boxes if you prefer not to use any of these.
> Please check out how to create custom meta boxes at https://developer.wordpress.org/plugins/metadata/custom-meta-boxes/. 
> Also, check out how to develop custom plugins at https://developer.wordpress.org/plugins/.

*Source: "Hands-on Nuxt.js Web Development", Packt Publishing, 2020, by Lau Tiam Kok, (ISBN ISBN 978-1-78995-269-8).*
*Chapter 18 "Creating a Nuxt App with a CMS and GraphQL Chapter 18"*
