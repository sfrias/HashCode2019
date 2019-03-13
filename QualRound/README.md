Python code for HashCode 2019 QualRound problem:

- Make a slideshow that links slides. One slide can include an horizontal photo, or two vertical photos.

- Photos has tags to link slides when were common with both:
  * If horizontal photo is included as slide, tags are contributed from photo.
  * If two vertical photos are included as slide, tags are contributed as union tags of both photos.
  
- Scoring: is the minimum value between:
  * Number of intersection tags betwenn this two slides.
  * Number of tags that be in first slide, but not in second slide.
  * Number of tags that be in second slide, but not in first slide.
