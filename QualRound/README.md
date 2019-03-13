Python code for HashCode 2019 QualRound problem:

- Make a slideshow that links slides. One slide can include an horizontal photo, or two vertical photos.

- Photos has tags to link slides when were common with both:
  * If horizontal photo is included as slide, tags are contributed from photo.
  * If two vertical photos are included as slide, tags are contributed as union tags of both photos.
  
- Scoring: is the minimum value between:
  * Number of intersection tags betwen this two slides.
  * Number of tags that be in first slide, but not in second slide.
  * Number of tags that be in second slide, but not in first slide.

Also the problem is NP-complete. Number of combinations of posible slides  in slideshow was a huge number, also we need to calculate possible combinations of vertical photos, grouped by two photos, for each slide with vertical photos.
