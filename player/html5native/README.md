# HTML5 native

If you aldready have access to an m3u8 player and simply need the link, please follow this procedure showing you how to do so.

To start implementing the DaCast library, you have two methods:

- Embed code
- Dynamic loading

## Embed code

```html
<!DOCTYPE html>
<html>
  <head>
    <script src="//player.dacast.com/js/player.js" id=CONTENT_ID player='html5native' class="dacast-video"></script>
  </head>
  <script>
    var myM3u8 = dacast.players['CONTENT_ID'];
    myM3u8.onReady( function() {
      myM3u8.getSrc( function(e) {
        console.log(e.url); //Containing m3u8 link with security.
      });
    });
  </script>
</html>
```

## Dynamic loading

```html
<!DOCTYPE html>
<html>
  <head>
    <script src="//player.dacast.com/js/player.js"></script>
  </head>
  <script>
    var myM3u8 = dacast('CONTENT_ID', 'DIV', {player:'html5native'});
      myM3u8.onReady( function() {
        myM3u8.getSrc( function(e) {
          console.log(e.url); //Containing m3u8 link with security.
        });
      });
  </script>
</html>
