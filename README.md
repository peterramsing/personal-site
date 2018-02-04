# peter.coffee

The personal site of Peter Ramsing.

## Build
* Requires [Jekyll](https://jekyllrb.com)
  * `$ gem install jekyll bundler`

### Development
* `$ jekyll s`

### Production
* `$ JEKYLL_ENV=production jekyll build`


## Deploy
For ease's sake I used Firebase for the hosting. Free + SSL and super quick for this application.

1. Have access to the Firebase project (email Peter)
1. Configure with that Firebase project (email Peter)
1. `$ firebase deploy`
  * **Important**: Only deploy a production build (see above)
