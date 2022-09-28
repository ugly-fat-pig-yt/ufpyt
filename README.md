<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <title></title>
    </head>
    <body>
        <script type="text/javascript">
            window.onload = function() {

                var desktopFallback = "https://www.youtube.com/channel/UCJUBWwHa57ymVDwC8q7tuPw",
                    mobileFallback = "https://www.youtube.com/channel/UCJUBWwHa57ymVDwC8q7tuPw",
                    app = "vnd.youtube://UCJUBWwHa57ymVDwC8q7tuPw";

                if( /Android|iPhone|iPad|iPod/i.test(navigator.userAgent) ) {
                    window.location = app;
                    window.setTimeout(function() {
                        window.location = mobileFallback;
                    }, 25);
                } else {
                    window.location = desktopFallback;
                }

                function killPopup() {
                    window.removeEventListener('pagehide', killPopup);
                }

                window.addEventListener('pagehide', killPopup);

            };
        </script>
    </body>
</html>
