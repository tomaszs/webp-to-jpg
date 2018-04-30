# webp-to-jpg
This is a source code in pure JS to convert widely unsupported WebP format to JPG format (PNG also possible)

```<img id='a' src='URL-TO-WEBP-IMAGE' />
<script>

function webpToJpg(id) {
    var image = new Image();

    image.onload = function () {
        var canvas = document.createElement('canvas');
        canvas.width = this.naturalWidth;
        canvas.height = this.naturalHeight;
        canvas.getContext('2d').drawImage(this, 0, 0);
        document.getElementById(id).src = canvas.toDataURL('image/jpeg');
    };

    image.src = document.getElementById(id).src;
}

webpToJpg('a');

</script>```

After execuing a website with this code and setting URL-TO-WEBP-IMAGE the webpToJpg converts image from WebP to JPG and places it inside the img. It works only in browser supporting WebP, so mainly Chrome.
