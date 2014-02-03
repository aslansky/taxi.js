# Bundle Loader [![devDependency Status](https://david-dm.org/aslansky/bundle-loader/dev-status.png)](https://david-dm.org/aslansky/bundle-loader#info=devDependencies)

[![browser support](https://ci.testling.com/aslansky/bundle-loader.png)](https://ci.testling.com/aslansky/bundle-loader)

Loads javascript bundles on demand or on click.
Bundles are combined files of javascript code you would generate with grunt, gulp or other build tools.

## Options

```
{
  // path to the bundle files
  path: '/',
  // html attribute
  attr: 'data-require',
  // load automatically on Loader()
  autoload: true,
  // store scripts in localStorage
  store: true,
  // prefix for localStorage objects
  storagePrefix: 'loader-',
  // default expire time in hours (2h)
  expiration: 2,
  // invalidation string, if changed stored object will be invalidated
  cacheBuster: ''
}
```

## Usage ##

```
var loader = Loader({
  path: '/javascript/build/'
})
.bundle(function (type, bundle, error, errorObj) {
  // type is 'loaded' or 'error'
  // bundle loaded or error
})
.done(function (loaded, failed) {
  // all bundles loaded
});
```

```
<div data-require="bundle-name"></div>
```

### On click loading ###

```
var loader = Loader({
  path: '/javascript/build/'
});

loader.onclick(selector, 'bundle-name', loadEnd, loadStart);
```
