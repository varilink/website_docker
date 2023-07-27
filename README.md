# Website - Docker

David Williamson @ Varilink Computing Ltd

-----

Docker Compose project for developing and testing the Varilink Computing Ltd website on the desktop. 

## Contents


## Usage

### Install Node Dependencies

Theme:
```sh
docker-compose run --rm --volume="$PWD/wordpress/theme/:/home/npm/" npm install
```

### Build Client Assets

Bootstrap CSS files generated using Saas (expanded style)
```sh
docker-compose run --rm --entrypoint=npx --volume="$PWD/wordpress/theme/:/home/npm/" npm sass /home/npm/assets/scss/custom.scss /home/npm/assets/css/bootstrap.css
```
Create the directory `wordpress/theme/assets/css` beforehand if it doesn't already exist.

Bootstrap CSS files generated using Saas (compressed style)
```sh
docker-compose run --rm --entrypoint=npx --volume="$PWD/wordpress/theme/:/home/npm/" npm sass --style=compressed /home/npm/assets/scss/custom.scss /home/npm/assets/css/bootstrap.min.css
```
Create the directory `wordpress/theme/assets/css` beforehand if it doesn't already exist.

Theme images generated using GIMP:
```sh
docker-compose run --rm gimp
```
Create the directory `wordpress/theme/assets/img` beforehand if it doesn't already exist.


