# The protocol for labeling unmanned aerial vehicle images (UAV images)

This protocol is used for UAV snapshots delineation (labeling/markup)
for solving tree species identification problem using
deep learning approach.

1. Make sure that the source image files (UAV images) have unique names (if those were obtained, e.g. from different sources);
2. This protocol requires that the origin of an image is expected to be in left upper corner of the image;
3. Create a csv-file that has the following columns: filename,xul,yul,xlr,ylr,type
   Where filename -- name of the image file; xul, yul, xlr, ylr -- the object bounding box coordinates on the image (in pixels); xul -- x coordinate of upper left corner;
   yul -- y coordinate of upper left corner; xlr -- x coordinate of lower right corner;
   ylr -- y coordinate of lower right corner; type -- object type (e.g. tree type, i.e.
   *betula mandsurica*, *quercus mongolica*). It is highly desirable that the type column
   is filled with simple values, e.g. betula, quercus (i.e. short unique names without spaces), encoded names are allowed too (i.e. you can use, e.g. 0 for betula and 1 for quercus).

   As an alternative csv file structure, you can use the following: filename,xul,yul,width,height,type. The width and height parameters are width and height of
   object's bounding box. Other parameter descriptions are given above.

   Once you choose the csv file structure, you should follow it (don't switching between
   them).

4. If source image was occasionally changed, don't save these changes.
5. You can use MS Paint to find coordinates of object's bounding box and MS Excel
   to fill up the csv file.

    ![Sample Image](https://raw.githubusercontent.com/deepeco/uavmarkup/master/images/select_obj.png =700x)

6. If objects are overlapped, the object which is marked up with the bounding box (bbox) should cover at least 50% of the bbox area (the more the better).

7. Finally, your csv-file should be something like this:

| filename        | xul | yul | xlr | ylr | type  |
|-----------------|-----|-----|-----|-----|-------|
| uniqueName1.jpg | 34  | 23  | 120 | 153 | tilia |
| uniqueName1.jpg | 260 | 150 | 320 | 188 | pinus |
| uniqueName2.png | 150 | 117 | 170 | 140 | pinus |






