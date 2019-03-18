Python code for HashCode 2019 QualRound problem:

- Make a slideshow that links slides. One slide can include an horizontal photo, or two vertical photos. Transitions must be some tags in common between two slides.

- Photos has tags to link slides when were common with both:
  * If horizontal photo is included as slide, tags are contributed from photo.
  * If two vertical photos are included as slide, tags are contributed as union tags of both photos.
  
- Scoring: is the minimum value between: note the scoring is symmetric. We can grow the slideshow in both directions.
  * Number of intersection tags betwen this two slides.
  * Number of tags that be in first slide, but not in second slide.
  * Number of tags that be in second slide, but not in first slide.

Best productive link with two slides: it occurs when there are the same tags in the intersection, that there are in any of the two linked slides, which are not in the other. Best ratio is 1 Point : 3 Tags

Also the problem is NP-complete. Number of combinations of posible slides  in slideshow was a huge number, also we need to calculate possible combinations of vertical photos, grouped by two photos, for each slide with vertical photos.

Now, we start with a look for data: some aditional auxiliary functions were created:

 - Load Data, returns:
  * *photos*: a list with photo Id (integer:0-(N-1), Number of tags for photo Id, Orientation: {'H','V'}, set of string tags.
  * *dtags*: a dictionary with tags occurrences for each tags, for all photos.
  * *tag_ph*: a photos list that contain a tag, for each tag(linkable), indexed by *dtag_ph*.
  * *dtag_ph*: a dictionary  pointer to *tag_ph* photos list, for each tag included in *photos* list.
  * Generic parameters: *nphotos* number of photos, *nv* number of vertical photos, *nh* number of horizontal photos,
    *nctags* default set() not connected tags, *ncphotos* default set() not connected photos, *ttags* Tag global number
    occurrences.

First approach is set a seed slide, and link options from/to this slide, alias Slide_L, Slide_R, and store this with scoring:
- First optimization was to make a matrix to set associations with tags and photo id's. Only calculate one time presence of tag on photo, or what photos have one specific tag. For lovely landscapes: 80.000 photos dataset, and a 840.000 different tags, we would be around 68 GB of memory words. So much.
- Second option is to work with dictionaries and sets, to optimize processing, and not overload memory.
![alt text](https://github.com/sfrias/HashCode2019/blob/master/QualRound/loaddata.jpg)
