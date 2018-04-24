# simple-rel-preload-polyfill

Help solve loading CSS blocking in PageSpeed Insights
```
<script>
    //
    // rel="preload" polyfill ignore if browser Chrome
    if(!/chrome/i.test(window.navigator.userAgent)) {
        try {
            document.createElement('link').relList.supports('preload');
        } catch (error) {
            for (var i = 0, array = document.querySelectorAll('[rel="preload"][as="style"]'); i < array.length; i++) {
                array[i].rel = 'stylesheet';
            }
        }
    }
</script>
```
