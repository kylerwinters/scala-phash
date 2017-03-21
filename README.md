# Scala pHash

Scala fork of [pHash](http://phash.org) library. This library identifies whether images are similar.  
Original pHash uses CImg library for image processing but I could not find CImg for jvm. Therefore I use ```java.awt``` and [scrimage](https://github.com/sksamuel/scrimage) for image processing. Consequently, results of my library is different from original phash.  
# How to use
My library impliments three Perceptual Hashing algorithms: Radial Hash, DCT hash and Marr hash. [More info about it](http://www.phash.org/docs/pubs/thesis_zauner.pdf).
```
val img1rad = PHash.radialHash(img1)
val img2rad = PHash.radialHash(img2)

println(PHash.radialHashDistance(img1rad, img2rad))
```

Radial distance is more when images are similar. 
DCT and marr distances are less when images are similar. 

<img width='200px' src='https://github.com/poslegm/scala-phash/blob/master/src/test/resources/example2.jpg'>
<img width='200px' src='https://github.com/poslegm/scala-phash/blob/master/src/test/resources/example4.jpg'>

```
radial: 0.9544747673204416
dct: 1
marr: 0.359375
```

<img width='200px' src='https://github.com/poslegm/scala-phash/blob/master/src/test/resources/1.jpg'>
<img width='200px' src='https://github.com/poslegm/scala-phash/blob/master/src/test/resources/2.jpg'>

```
radial: 0.37825891435315523
dct: 36
marr: 0.4947916666666667
```

# Warning
My results is not compatible with original pHash. Use original library if you have an opportunity.  
Also, it works very slow compared with c++ version.
# Thanks
* [pHash](http://phash.org) / [https://github.com/clearscene/pHash](https://github.com/clearscene/pHash) 
* [jphash](https://github.com/pragone/jphash)
* [scrimage](https://github.com/sksamuel/scrimage)
