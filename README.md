# Integer 32, LLC Logos

## Trademark, Copyright, and License

These logos are owned by Integer 32, LLC. If you'd like to use these
logos in any capacity, please [contact us][website].

[website]: http://www.integer32.com/

## Specifications

Font: Montserrat-Regular

|            | Hex     | CMYK        | Pantone  |
|------------|---------|-------------|----------|
| Dark Blue  | #364d9e | 91 81 1 0   | 102-15 C |
| Light Blue | #a6d0ec | 32 7 1 0    | 112-10 C |
| Outline    | #3e4555 | 76 66 47 34 | 174-15 C |

## Conversion to PNG

Inkscape can be used to convert the SVG to a PNG:

```
inkscape -z -e out.png -h 64 in.svg
```

* `-z` - no GUI
* `-e` - export as PNG
* `-h` - desired height in pixels
* `-w` - desired width in pixels (to preserve aspect ratio, don't use with height)

Note that on OS X, Inkscape needs the absolute path to input and output files.

### Favicons

These need to be square, so we can use Imagemagick to pad the non-square PNG

```
for i in 32 48 62 192 512; do
    in="/tmp/badge.svg"
    out="/tmp/favicon-${i}.png"
    size="${i}x${i}"

    # Convert to PNG
    inkscape -z -e "${out}" -h "$i" "${in}"
    # Pad out the PNG to make it square
    mogrify -background none -gravity center -extent "${size}" "${out}"
done
```
