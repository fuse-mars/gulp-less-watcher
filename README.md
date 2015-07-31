# Gulp Less Watcher

Watches Less files (and imports) using an endless streaming interface (and generates sourcemaps).

## Usage

```bash
npm install gulp-less-watcher --save-dev
```

```javascript
import gulp        from 'gulp';
import loadPlugins from 'gulp-load-plugins';

const $ = loadPlugins();
const config = {
  // Less config...
};

return gulp.src('main.less', { cwd: 'resources/assets/styles/' })
  .pipe($.lessWatcher(config))
  .pipe($.sourcemaps.init())
  .pipe($.less(config))
  .pipe($.sourcemaps.write('./', { includeContent: true }))
  .pipe(gulp.dest('public/assets/'));
```