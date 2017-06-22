---

title: Divided-area-based rendering device and divided-area-based rendering method
abstract: A divided-area-based rendering device includes: a table generating unit that calculates, for each unit polygon, a first area including the unit polygon, using screen coordinates, determines, from among divided areas obtained by dividing a rendering region, a divided area including at least part of the first area, and generates an area-by-polygon table that is a table in which, for each unit polygon, the divided area including the at least part of the first area including the unit polygon is associated with the unit polygon; a determining unit that determines a rendering unit polygon that is one of the unit polygons which is associated with the divided area, by referring to the area-by-polygon table; and an area rendering unit that performs, for each divided area, vertex processing and rasterization on the rendering unit polygon.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09299182&OS=09299182&RS=09299182
owner: Panasonic Intellectual Property Management Co., Ltd.
number: 09299182
owner_city: Osaka
owner_country: JP
publication_date: 20131030
---
The present invention relates to three dimensional graphics rendering and in particular to a divided area based rendering device that performs processing for each of divided areas obtained by dividing a rendering region.

In the three dimensional graphics rendering known is a technique for dividing a rendering region into rectangular areas blocks or tiles and processing the rectangular areas. In this technique an internal memory accessible at a high speed is used as a memory for the rectangular areas. With this an external memory is not accessed while the memory of the rectangular areas is accessed for rasterization and thus it is possible to reduce a memory bandwidth and power consumption see Patent Literature PTL 1 for instance .

A divided area based rendering device that performs area division is expected to reduce an amount of intermediate data used for rendering.

In view of this an object of the present invention is to provide a divided area based rendering device that performs area division and reduces an amount of intermediate data used for rendering.

A divided area based rendering device according to one aspect of the present invention includes a command receiving unit configured to receive a rendering command indicating a plurality of unit polygons which are to be rendered in a rendering region and each of which includes one or more polygons a coordinate converting unit configured to convert for each of the unit polygons indicated in the rendering command vertex coordinates of the unit polygon in a three dimensional space into screen coordinates in a two dimensional plane a table generating unit configured to i for each unit polygon calculate a first area including the unit polygon in the two dimensional plane using the screen coordinates and compute among a plurality of divided areas obtained by dividing the rendering region a divided area including at least part of the first area and ii generate using results of the computation for the unit polygons an area table that is a table in which for each unit polygon the divided area including the at least part of the first area including the unit polygon is associated with the unit polygon a determining unit configured to determine a rendering unit polygon for each of the divided areas by referring to the area table the rendering unit polygon being one of the unit polygons which is associated with the divided area and an area rendering unit configured to perform for each divided area vertex processing and rasterization on the rendering unit polygon.

It is to be noted that this generic and specific aspect may be implemented using a system a method an integrated circuit a computer program or a non transitory computer readable recording medium such as a compact disc read only memory CD ROM and may also be implemented by any combination of systems methods integrated circuits computer programs and recording media.

The present invention can provide a divided area based rendering device that performs area division and reduces an amount of intermediate data used for rendering.

The technique for dividing a rendering region into rectangular areas and processing the rectangular areas has the unique divided area based rendering problem that to process the rectangular areas a polygon included in a scene needs to be loaded as many times as the number of the rectangular areas.

In order to solve this problem it is possible to apply a method for holding for each divided area rectangular area a visible polygon list and referring only to the visible polygon list of the divided area when the divided area is rendered. The following describes this method.

The divided area based rendering device shown in includes a polygon shape processing unit and a rasterizing unit .

The polygon shape processing unit includes a command receiving unit a coordinate converting unit a polygon area calculating unit and a list holding unit .

The command receiving unit fetches a display list held in a display list holding unit and decodes the display list into a rendering command .

The coordinate converting unit fetches from a polygon data holding unit vertex coordinates A indicating a shape of a polygon that is to be rendered and is indicated in the rendering command and converts the vertex coordinates A into screen coordinates .

The polygon area calculating unit determines by culling whether polygons are visible or invisible using the screen coordinates . Next the polygon area calculating unit determines for each divided area whether a polygon determined to be visible is visible and generates a polygon by area list indicating for each divided area the visible polygon.

As stated above the polygon shape processing unit does not rasterize all polygons in a scene but generates the polygon by area list . The polygon by area list is a list that indicates polygons which potentially belong to respective divided areas.

The rasterizing unit includes a polygon list obtaining unit and an area rendering unit . The polygon list obtaining unit obtains the polygon by area list generated by the polygon shape processing unit .

The area rendering unit loads for each divided area polygon data B of a polygon visible in a divided area to be processed and indicated in the polygon by area list performs vertex processing and rasterization on the polygon data B and transfers to an external memory pixel data resulting from the processing and the rasterization.

The polygon by area list holds information indicating a polygon determined to be visible in a divided area. The area rendering unit fetches from the polygon data holding unit the polygon data B including unconverted polygon information and vertex attribute data representing the polygon and performs the vertex processing the rasterization and transfer processing on the polygon data B. At this time reading and writing of pixels by a blend are performed on a rendering internal memory accessible at a high speed using the rendering internal memory as a memory for the divided areas. With this the external memory is not accessed and thus it is possible to produce effects such as a reduction in a memory bandwidth and a reduction in power consumption.

As just described in the divided area based rendering device according to the comparative example the polygon shape processing unit generates and holds the polygon by area list that indicates for each divided area the visible polygon. With this it is possible to achieve divided area based rendering without loading unnecessary polygon data at the time of the rasterization.

With the configuration of the comparative example however polygon information is held for each divided area. As a result the inventors have found that when a lot of visible polygons are in a scene a memory region for generating and holding the polygon by area list increases in size.

In an extreme example if a polygon spreads over all divided areas information about the polygon is registered for all the divided areas in the polygon by area list . For this reason in the worst scenario the polygon by area list is required to hold information items as many as the number of the divided areas the number of all polygons. Thus a lot of memory regions are necessary.

Moreover the size of the memory region for the polygon by area list cannot be fixed until the polygon shape processing unit actually performs processing. Consequently the inventors have found that the divided area based processing must be interrupted for a scene including visible polygons whose information exceeds the capacity of a previously reserved memory region.

A divided area based rendering device according to one aspect of the present invention includes a command receiving unit configured to receive a rendering command indicating a plurality of unit polygons which are to be rendered in a rendering region and each of which includes one or more polygons a coordinate converting unit configured to convert for each of the unit polygons indicated in the rendering command vertex coordinates of the unit polygon in a three dimensional space into screen coordinates in a two dimensional plane a table generating unit configured to i for each unit polygon calculate a first area including the unit polygon in the two dimensional plane using the screen coordinates and compute among a plurality of divided areas obtained by dividing the rendering region a divided area including at least part of the first area and ii generate using results of the computation for the unit polygons an area table that is a table in which for each unit polygon the divided area including the at least part of the first area including the unit polygon is associated with the unit polygon a determining unit configured to determine a rendering unit polygon for each of the divided areas by referring to the area table the rendering unit polygon being one of the unit polygons which is associated with the divided area and an area rendering unit configured to perform for each divided area vertex processing and rasterization on the rendering unit polygon.

With this configuration the divided area based rendering device is capable of generating the area table indicating for each polygon unit the divided area included in the first area corresponding to the unit polygon and determining the target unit polygon for the target divided area by referring to the area table in divided area based rendering. Thus for instance the divided area based rendering device is capable of reducing an amount of data of the table when a lot of unit polygons to be rendered are present as compared to a case where a table indicating for each divided area a polygon to be processed is used.

For example the area table may include a fixed number of entries the table generating unit may store into each of the entries area information indicating the divided area including the at least part of the first area and associated with the unit polygon when the number of the unit polygons is greater than the fixed number the table generating unit may divide the unit polygons into the fixed number of groups each of which includes at least one unit polygon for each of the fixed number of the groups calculate a second area including the at least one unit polygon in the two dimensional plane which is included in the group using the screen coordinates and compute among the divided areas a divided area including at least part of the second area and generate using results of the computation for the fixed number of the groups the area table that is a table in which for each group the divided area including the at least part of the second area including the at least one unit polygon included in the group is associated with the group and the determining unit may determine the rendering unit polygon for each of the divided areas by referring to the area table the rendering unit polygon being among the unit polygons a unit polygon included in the group associated with the divided area.

With this configuration the divided area based rendering device is capable of generating the area table having a predetermined amount of data even when a lot of unit polygons to be rendered are present.

For instance the table generating unit may sequentially select as a target unit polygon one of the unit polygons generate for each of the selected target unit polygons the area information about the target unit polygon and store the area information into among the entries an entry that does not hold the area information determine when storing area information about a new unit polygon into an entry whether the number of area information items stored in the area table is greater than the fixed number as a result of storing the area information calculate when the number of the area information items is greater than the fixed number the second area including the new unit polygon and the unit polygon corresponding to the area information stored in a selected entry that is one of the entries using the area information stored in the selected entry and the area information about the new unit polygon and store into the selected entry the area information indicating the divided area including the at least part of the calculated second area.

For example the table generating unit may sequentially select as a target unit polygon one of the unit polygons generate for each of the selected target unit polygons the area information about the target unit polygon and store the area information into among the entries an entry that does not hold the area information determine when storing area information about a new unit polygon into an entry whether the number of area information items stored in the area table is greater than the fixed number as a result of storing the area information calculate when the number of the area information items is greater than the fixed number the second area including the unit polygon corresponding to the area information stored in a first entry among the entries and the unit polygon corresponding to the area information stored in a second entry among the entries using the two area information items stored in the first entry and the second entry store into the first entry the area information indicating the divided area including the at least part of the calculated second area and store into the second entry the area information about the new unit polygon.

With this configuration the divided area based rendering device is capable of storing area information items about unit polygons adjacent to each other in rendering order into one entry. Since generally the unit polygons adjacent to each other in rendering order often have relatively close rendering locations the divided area based rendering device is capable of increasing the accuracy of the area information items.

With this configuration the divided area based rendering device is capable of reducing the amount of data of the area information.

For example the area information may indicate among vertices of the first area vertices that are diagonal to each other.

With this configuration the divided area based rendering device is capable of reducing the amount of data of the area information.

For instance the area information has a predetermined number of bits each one of which is associated with a different one of unit areas each including one or more of the divided areas and the one bit indicates whether the unit area associated with the one bit includes the at least part of the first area corresponding to the unit polygon corresponding to the entry.

With this configuration when the unit polygons are divided into the fixed number of groups the divided area based rendering device is capable of suppressing the designation of an unnecessary area in area information.

For example the area information may include first information indicating a divided area including among vertices of the first area vertices that are diagonal to each other and second information having a predetermined number of bits each of which is associated with a different one of unit areas each including the divided areas the one bit indicates whether the associated unit area includes the at least part of the first area corresponding to the unit polygon corresponding to the entry and the determining unit may determine a unit polygon as the rendering unit polygon for each of the divided areas the unit polygon being one of the unit polygons which is associated with the divided area in the first information and with the unit area including the divided area in the second information.

With this configuration when the unit polygons are divided into the fixed number of groups the divided area based rendering device is capable of suppressing the designation of an unnecessary area in area information and the decrease in accuracy of designating an area.

For instance the coordinate converting unit may further determine using the screen coordinates whether each of the unit polygons is a valid unit polygon or an invalid unit polygon the valid unit polygon being a unit polygon at least part of which is displayed in the rendering region and the invalid unit polygon being a unit polygon whole of which is not displayed in the rendering region the table generating unit may store the area information into the entry when the target unit polygon is the invalid unit polygon the area information indicating that the target unit polygon is the invalid unit polygon and the determining unit may exclude the target unit polygon from a rendering target when the area information in the area table indicates that the target unit polygon is the invalid unit polygon.

With this configuration the determining unit is capable of easily determining which unit polygon each entry included in the area table belongs to.

For example the coordinate converting unit may further divide the unit polygon into a plurality of divided unit polygons by clipping using the screen coordinates and the table generating unit may calculate the first area including all of the divided unit polygons when the clipping is performed on the target unit polygon and store into one of the entries the area information indicating the divided area including the at least part of the calculated first area.

With this configuration the divided area based rendering device is capable of storing area information items about the unit polygons divided by clipping into one entry.

For instance the table generating unit may sequentially select as target unit polygons the unit polygons according to an order of data of the unit polygons included in the rendering command and the determining unit may associate using the order the unit polygons and the area information items stored in the entries.

With this configuration the determining unit is capable of easily determining which unit polygon each entry included in the area table corresponds to.

For example the coordinate converting unit may further determine using the screen coordinates whether each of the unit polygons is a valid unit polygon or an invalid unit polygon the valid unit polygon being a unit polygon at least part of which is displayed in the rendering region and the invalid unit polygon being a unit polygon whole of which is not displayed in the rendering region the table generating unit may further count among the unit polygons the number of the valid unit polygons that are consecutive and the number of the invalid unit polygons that are consecutive and generate a polygon attribute table indicating the number of the consecutive valid unit polygons and the number of the consecutive invalid unit polygons and the determining unit may further determine by referring to the polygon attribute table whether each of the unit polygons is the valid unit polygon or the invalid unit polygon and determine the rendering unit polygon for each of the divided areas by referring to the area table the rendering unit polygon being one of the valid unit polygons which is associated with the divided area.

With this configuration only the area information about the valid unit polygon is stored into the area table. This allows the divided area based rendering device to reduce the amount of data of the area table.

For instance the unit polygon may be a polygon group including a plurality of polygons the table generating unit may generate as the area table i a first area table that is a table in which for each of a plurality of the polygon groups the divided area including the at least part of the first area including the polygon group is associated with the polygon group and ii a second area table that is a table in which for each of the polygons the divided area including the at least part of the first area including the polygon is associated with the polygon the determining unit may determine for each of the divided areas a rendering polygon group by referring to the first area table the rendering polygon group being one of the polygon groups which is associated with the divided area and a rendering polygon by referring to the second area table the rendering polygon being one of the polygons which is associated with the divided area and the area rendering unit may perform for each divided area the vertex processing and the rasterization on the rendering polygon.

With this configuration the divided area based rendering device is capable of reducing an amount of processing in the determination processing using the determination on a polygon group by polygon group basis and the determination on a polygon by polygon basis.

It is to be noted that these generic and specific aspects may be implemented using a system a method an integrated circuit a computer program or a non transitory computer readable recording medium such as a compact disc read only memory CD ROM and may also be implemented by any combination of systems methods integrated circuits computer programs and recording media.

Hereinafter a divided area based rendering device according to one aspect of the present invention is described in detail with reference to the drawings.

It is to be noted that the exemplary embodiments described below each show a general or specific example. The numerical values shapes materials structural elements the arrangement and connection of the structural elements etc. shown in the following embodiments are mere examples and therefore do not limit the present invention. In addition among the structural elements in the following embodiments structural elements not recited in any one of the independent claims are described as arbitrary structural elements.

A divided area based rendering device according to Embodiment 1 determines for each of polygons a divided area including the polygon from among divided areas and generates an area by polygon table that is a table in which for each polygon the divided area included in the polygon is associated with the polygon. Then the divided area based rendering device determines for each divided area a polygon to be processed that is among the polygons a polygon associated with a divided area to be processed in the area by polygon table.

With this the divided area based rendering device is capable of reducing an amount of data of the table when a lot of polygons to be processed are present as compared to a case where a table indicating for each divided area a polygon to be processed is used.

First the following describes a basic configuration of the divided area based rendering device according to this embodiment.

The command receiving unit receives a rendering command indicating polygons to be rendered in a rendering region.

The coordinate converting unit obtains for each of the polygons indicated in the rendering command polygon data including vertex coordinates of the polygon in a three dimensional space and converts the vertex coordinates into screen coordinates in a two dimensional plane.

The table generating unit calculates for each polygon a first area including the polygon in the two dimensional plane using the screen coordinates of the polygon. Next the table generating unit computes for each polygon among divided areas obtained by dividing the rendering region a divided area including at least part of the first area. Subsequently the table generating unit generates using the computation results for the polygons an area by polygon table that is a table in which for each polygon the divided area including the at least part of the first area including the polygon is associated with the polygon.

The determining unit determines for each of the divided areas a rendering polygon that is one of the polygons which is associated with a divided area to be processed by referring to the area by polygon table .

The area rendering unit generates for each divided area pixel data by performing vertex processing and rasterization on the rendering polygon.

The divided area based rendering device shown in includes a polygon shape processing unit and a polygon by area rendering unit .

The polygon shape processing unit generates an area by polygon table that is a table in which divided areas are associated with polygons. The polygon by area rendering unit performs rendering for each of the divided areas using the area by polygon table .

The polygon shape processing unit includes a command receiving unit A a coordinate converting unit a table generating unit a table holding unit and a divided area setting unit . The polygon by area rendering unit includes a command receiving unit B a determining unit an area rendering unit and a rendering region setting unit .

The divided area setting unit sets a size and a division number for rectangular divided areas. The procedure of divided area based rendering is described with reference to and . In the divided area based rendering a final rendering region is divided into divided areas 0 to 31 smaller than the final rendering region . Then rendering is performed for each of the divided areas . shows a case where the final rendering region is divided horizontally by eight and vertically by four that is by a total of 32.

Generally an internal memory region having the same size as data of each of the divided areas is used as an area rendering destination. Thus only the access to the internal memory region is performed as access to pixel data in the rendering of each divided area. In other words an external memory that holds data of the final rendering region is not accessed. Moreover every time the rendering of each divided area is completed the data of the processed divided area is transferred as data of a position corresponding to the final rendering region to the external memory. For this reason the internal memory region needs to have a size greater than or equal to a size large enough to include the data of the divided area .

Where a width and a height of the final rendering region are respectively denoted by W and H and a width and a height of the divided areas are respectively denoted by BW and BH the number of the divided areas horizontally arranged XNUM is calculated by CEIL W BW and the number of the divided areas vertically arranged YNUM is calculated by CEIL H BH .

If the width W of the final rendering region cannot be divided by the width BW of the divided areas as shown in the areas and horizontally exceed the final rendering region by BW and the areas to vertically exceed the final rendering region by BH . Consequently transfer of portions of the areas in consideration of the fractions needs to be performed as transfer to the final rendering region .

It is to be noted that a method for setting a size and a division number of the divided areas which is performed by the divided area setting unit may be a given method. For instance at least one of the size and the division number of the divided areas may be predetermined. The divided area setting unit outputs the set sizes BW and BH and division numbers XNUM and YNUM of the divided areas to the table generating unit .

The command receiving units A and B correspond to the command receiving unit shown in . The display list holding unit holds a display list including rendering commands . The polygon data holding unit holds polygon data of polygons.

First the command receiving unit A receives a rendering command included in the display list held in the display list holding unit and interprets the rendering command S . This rendering command includes a pointer for polygon data .

Specifically as shown in the rendering command includes 1 rendering context information necessary for rendering and displaying a polygon 2 information indicating a polygon data address 3 information indicating the number of vertices of a polygon 4 information indicating a start of polygon rendering and so on. Moreover the display list that is a rendering command group includes address setting to the polygon data . As stated above in a general configuration the polygon data is stored in a memory region different from a memory region of the display list.

The command receiving unit A fetches a rendering start command indicating a start of polygon rendering and informs the coordinate converting unit of the fetching.

Next the coordinate converting unit loads vertex coordinates A of each of polygons for which the rendering command specifies the start of rendering and converts the vertex coordinates A into screen coordinates S . Specifically the coordinate converting unit refers to a polygon data address placed before the rendering start command and loads the vertex coordinates A in the polygon data stored at the address.

Here the polygon data includes as vertex data attribute data B attribute data along with the vertex coordinates A indicating positional coordinates in the three dimensional space. The attribute data B includes information indicating a vertex color a normal line and texture coordinates. Moreover the vertex coordinates A are normally represented by a position x y z in the three dimensional space. The coordinate converting unit converts the three dimensional position into a two dimensional position X Y representing screen coordinates.

The coordinate conversion is a known technique in general 3D graphics but the following describes a summary of the coordinate conversion with reference to and .

A polygon triangle P0 P1 P2 at vertex coordinates A is represented by a model coordinate system x y z that is positional coordinates in the three dimensional space. The coordinate converting unit converts the points P0 P1 and P2 indicated by the vertex coordinates A into points P0 P1 and P2 in a camera coordinate system x y z having a viewpoint position C in the three dimensional space as the origin and an eye direction of z . Moreover the coordinate converting unit performs projective transformation in which the points P0 P1 and P2 are projected onto a screen to compute points SP0 SP1 and SP2 screen coordinates in a screen coordinate system X Y .

The screen coordinates indicate at which position in a final rendering region a polygon is. Thus the screen coordinates can be used to determine which divided area the polygon belongs to. The coordinate converting unit transmits to the table generating unit the screen coordinates of the vertices of the polygon.

Furthermore the coordinate converting unit performs only the culling determination but not culling itself. When all the vertices of the polygon are out of the final rendering region the polygon is not rasterized finally and becomes unnecessary. The culling is processing for deleting this unnecessary polygon itself at a coordinate conversion stage. It is to be noted that the deletion of a polygon means excluding a polygon from a rendering target.

The culling determination is processing for only determining whether all vertices of a polygon are out of a final rendering region. In other words the coordinate converting unit determines for each polygon whether the polygon is a valid polygon at least part of which is displayed in a rendering region or an invalid polygon the whole of which is not displayed in the rendering region using the screen coordinates .

Moreover the coordinate converting unit adds an invalid flag to a polygon to be culled and transmits the invalid flag together with the screen coordinates of the polygon to the table generating unit .

Furthermore the coordinate converting unit may perform clipping other than the above processing. The clipping is well known processing for setting when some of vertices of a polygon are 1 behind a viewpoint position C or 2 out of a final rendering region the polygon within a region in the field of view by cutting part of the polygon out of the final rendering region.

The following describes the clipping. and each are a diagram illustrating the clipping. When a vertex P2 in the camera coordinate system is behind a viewpoint position has a negative Z coordinate coordinates SP2 resulting from simple application of projective transformation cannot be converted into accurate screen coordinates as shown in . In view of this as shown in the coordinate converting unit clips sides of a polygon at a Z coordinate ahead of the viewpoint position before the projective transformation. This enables the conversion into the accurate screen coordinates.

In this example the coordinate converting unit calculates a side P1 P2 and a side P0 P2 connected to the vertex P2 having the negative Z coordinate and intersection points CP0 and CP1 on Z N N 0 plane. Next the coordinate converting unit applies the projective transformation to CP0 and CP1 to derive screen coordinates SCP0 and SCP1. In this manner the coordinate converting unit generates a polygon SP0 SP1 SCP0 and a polygon SP0 SCP0 SCP1. To put it differently the coordinate converting unit divides the polygon into divided polygons by performing the clipping using the screen coordinates .

When one polygon is divided into polygons through the clipping the coordinate converting unit adds to the divided polygons a clipping state flag indicating that the polygons have been generated from the same polygon. Then the coordinate converting unit transmits a set of the screen coordinates of the polygons obtained by dividing the one polygon along with the clipping state flag to the table generating unit .

It is to be noted that when all vertices of the polygons are out of the final rendering region as the result of the clipping division as with the time of the culling determination the coordinate converting unit transmits the screen coordinates of the polygons along with the invalid flag to the table generating unit without deleting the polygons.

Moreover as stated above the polygon data includes not only the vertex coordinates A but also the attribute data B such as texture reference coordinates a vertex color and a vertex normal vector. The coordinate converting unit may load only the vertex coordinates A which are necessary for calculating the screen coordinates and are in the polygon data or may load the vertex coordinates A with the attribute data B that are grouped. When however the vertex coordinates A are loaded with the attribute data B a time required for loading and an amount of memory access increase accordingly. Moreover the coordinate conversion itself may be achieved with a program such as a code or may be hard wired.

Next the table generating unit calculates using the screen coordinates for each polygon and the number and size of the divided areas area information of the polygon to generate the area by polygon table that is a table in which the area information items are associated with the respective polygons S . The area information is information indicating a divided area to which a polygon belongs. For example the area information is information indicating a boundary box. The boundary box is the smallest rectangle including a whole polygon. It is to be noted that the area information may be information indicating a first area including a polygon or information indicating something other than the boundary box. Moreover the area information is for instance information indicating a divided area including at least part of the first area.

When the final rendering region is divided horizontally into eight divided areas and vertically into four divided areas the 32 divided areas are present which have area IDs ranging from 0 to 31. In three vertices A to C representing a polygon belong to the respective divided areas having the area IDs 3 25 and 21. A boundary box of the polygon is the smallest rectangle including the vertices A to C. Moreover among the four vertices representing the boundary box the vertex and the vertex that are diagonal to each other are in the divided areas having the area IDs 1 and 29. The table generating unit stores as area information the two area IDs including the vertex and the vertex into the area by polygon table .

It is to be noted that although illustrates the example where the area IDs are managed one dimensionally as shown in the boundary box may be managed with two dimensional area IDs in a horizontal direction and a vertical direction. In the boundary box is represented as XID YID 1 0 5 3 .

The following describes a method for calculating area information for various polygon patterns with reference to and .

All vertices of a polygon are within a final rendering region . In this case area information is represented by a set of 0 0 and 3 2 that are the minimum area ID and the maximum area ID respectively of a rectangular area including the polygon .

All vertices of a polygon belong to the same divided area. In this case area information is represented by a set of 6 3 and 6 3 that are the minimum area ID and the maximum area ID respectively of a rectangular area including the polygon .

Some of vertices of a polygon are out of the final rendering region . In this case area information is represented by a set of 3 3 and 4 3 that are the minimum area ID and the maximum area ID respectively included in the final rendering region .

All of vertices of a polygon are out of the final rendering region . In this case an invalid flag indicating that the polygon is not to be rendered is added to the polygon . When an invalid flag is added to a polygon to be processed i.e. the polygon to be processed is an invalid polygon the table generating unit stores into an entry included in the area by polygon table area information indicating that the polygon to be processed is the invalid polygon. Specifically the table generating unit sets the maximum area ID value 7 3 of a divided area to the minimum area ID of the area information of the polygon to which the invalid flag is added and the minimum area ID value 0 0 of the divided area to the maximum area ID. In other words the table generating unit sets as the area information of the invalid polygon information indicating that the polygon belongs to none of the divided areas.

Polygons to each are a divided polygon obtained by dividing one polygon through the clipping. In this case area information indicates the union of boundary boxes of the divided polygons.

Specifically in the example shown in the boundary box of the polygon is represented by 5 0 and 7 0 the boundary box of the polygon is represented by 5 0 and 7 0 and the boundary box of the polygon is represented by 5 0 and 7 1 . Thus the boundary box for the polygons before the clipping division is represented by 5 0 and 7 1 .

A polygon is not a triangle but a point primitive having one vertex. A polygon is a line primitive having two vertices. As with a triangle primitive a rectangle enclosing a polygon may be calculated for the point primitive and the line primitive. However in the OpenGL ES specification that is standard application programming interface API specification for 3D graphics an API for changing a size of a point and an API for changing a width of a line exist for rendering point primitives and line primitives. For this reason a boundary box cannot be calculated with only the vertex coordinates and it is necessary to calculate a boundary box in consideration of a context such as the size of the point and the width of the line set by the APIs. For example as shown in it is necessary to set for area information of a point having a radius a set of 6 1 and 7 3 representing a boundary box in consideration of the radius. Moreover it is necessary to set for area information of a line having a line width a set of 4 0 and 5 1 representing a boundary box in consideration of the line width.

It is however not necessary to strictly calculate the area information and as long as it is guaranteed that a true area is included a simplified boundary box may be set as area information to reduce an amount of calculation.

For instance for the polygon that is the point primitive the table generating unit does not calculate a boundary box from a circle but may use as four vertices of the boundary box four points obtained by adding or subtracting the radius of the circle to or from vertex coordinates A that are the center of the circle.

Moreover for the polygon that is the line primitive the table generating unit does not calculate a rectangle with rotation as shown in but may calculate a total of eight points obtained by adding or subtracting a line width to or from each of two vertex coordinates representing lines and calculate a boundary box using the eight points.

First the table generating unit selects as a target polygon one of polygons to be rendered S . The table generating unit sequentially selects according to an order in which information items about the polygons are arranged in the rendering command a polygon starting from the polygon arranged first.

Next the table generating unit obtains from the coordinate converting unit screen coordinates an invalid flag and a clipping state flag of the target polygon S .

Next the table generating unit selects a valid vertex according to a primitive of the polygon S . Specifically when the polygon is a point primitive since only the one vertex has valid screen coordinates screen coordinates of other two vertices are not referred to in the subsequent calculation of a boundary box. Likewise when the polygon is a line primitive two vertices are selected as valid screen coordinates and when the polygon is a triangle primitive three vertices are selected as valid screen coordinates.

Next the table generating unit determines by referring to the invalid flag whether the target polygon is a valid polygon or an invalid polygon. Moreover the table generating unit determines by referring to the clipping state flag whether the target polygon is a divided polygon obtained through clipping S .

When a condition that the target polygon is the invalid polygon and is not the divided polygon is satisfied Yes in S the table generating unit sets the maximum area ID MaxID of the divided areas as the minimum area ID of area information and sets the minimum area ID MinID of the divided areas as the maximum area ID of the area information S . With this the area information indicates nonexistent areas. In other words the area information indicates that the polygon belongs to none of the divided areas. It is to be noted that the same effect can be produced by setting area information that satisfies the minimum area ID the maximum area ID.

Next the table generating unit stores the set area information the minimum area ID and the maximum area ID into one entry included in the area by polygon table S .

As stated above when the target polygon is the invalid polygon the table generating unit stores into the entry the area information indicating that the target polygon is the invalid polygon. Moreover when the area information indicates that the target polygon is the invalid polygon in the area by polygon table the determining unit excludes the target polygon from a rendering target.

In contrast when the target polygon is the valid polygon or the divided polygon No in S the table generating unit calculates the minimum coordinates and the maximum coordinates of a rectangle enclosing the target polygon. Specifically when the target polygon is not the divided polygon the table generating unit calculates using screen coordinates of a valid vertex the minimum coordinates and the maximum coordinates of the rectangle enclosing the target polygon. Then the table generating unit calculates using the number and a size of the divided areas an area ID of a divided area having the calculated minimum coordinates and an area ID of a divided area having the calculated maximum coordinates. Then the table generating unit sets the area ID of the divided area having the minimum coordinates to the minimum area ID and the area ID of the divided area having the maximum coordinates to the maximum area ID S . It is to be noted that when the minimum coordinates or the maximum coordinates are out of the final rendering region the table generating unit corrects the minimum coordinates or the maximum coordinates to coordinates of a position in the final rendering region closest to the minimum coordinates or the maximum coordinates.

Furthermore when the target polygon is the divided polygon the table generating unit sets an area ID indicating invalidity as area information the maximum area ID and the minimum area ID .

Next the table generating unit determines by referring to the clipping state flag whether the target polygon is a divided polygon obtained through clipping S .

When the target polygon is not the divided polygon No in S the table generating unit stores the minimum area ID and the maximum area ID calculated in step S into one entry included in the area by polygon table S .

In contrast when the target polygon is the divided polygon Yes in S the table generating unit determines whether the target polygon is a divided polygon at the start of clipping S . When the target polygon is the divided polygon at the start of clipping Yes in S the minimum area ID and the maximum area ID of the target polygon are directly held as an initial value.

In contrast if the target polygon is a divided polygon in the middle of clipping except for the start of clipping No in S the table generating unit updates the minimum area ID and the maximum area ID of a preceding divided polygon e.g. the divided polygon at the start of clipping using the minimum area ID and the maximum area ID of the polygon to be processed S . This processing corresponds to calculating the union of a boundary box of the preceding divided polygon and a boundary box of the polygon to be processed. Specifically the table generating unit selects a smaller one of the minimum area ID of the preceding divided polygon and the minimum area ID of the polygon to be processed and sets the selected minimum area ID to the updated minimum area ID. Moreover the table generating unit selects a larger one of the maximum area ID of the preceding divided polygon and the maximum area ID of the polygon to be processed and sets the selected maximum area ID to the updated maximum area ID.

Next the table generating unit determines whether the target polygon is a divided polygon at the end of clipping S . When the target polygon is not the divided polygon at the end of clipping No in S the table generating unit still needs to refer to other divided polygons included in a polygon before division. Thus the table generating unit selects the next polygon as the target polygon S and performs step S and the subsequent processing.

In contrast when the target polygon is the divided polygon at the end of clipping Yes in S a set of the minimum area ID and the maximum area ID held at the time indicates a boundary box of one polygon before division. Thus the table generating unit stores the minimum area ID and the maximum area ID into one entry included in the area by polygon table S .

As stated above when the clipping is performed on the target polygon the table generating unit calculates the first area including all the divided polygons and stores the area information indicating the divided area including at least part of the calculated first area into one of entries.

After step S or step S the table generating unit performs integration processing S . It is to be noted that this integration processing is described later.

When the above processing is not performed on all the polygons to be rendered No in S the next polygon is selected S and step S and the subsequent processing are performed on the selected polygon.

The area information thus calculated is registered in the area by polygon table . Here the area by polygon table is a table having a fixed number TMAX of entries. When the number of original polygons is less than or equal to TMAX area information about one original polygon is held per entry as shown in . In contrast when the number of the polygons is greater than TMAX area information items about polygons need to be held per entry.

When the number of the polygons is less than or equal to TMAX No in S the table generating unit does not perform the integration processing but stores area information about one polygon per entry in ascending order starting from Entry 0 .

In contrast when the number of the polygons is greater than TMAX Yes in S the table generating unit performs the integration processing. For instance when Polygon 8 is input since the number of the polygons exceeds the number of entries area information about one polygon cannot be held per entry. Then the table generating unit selects an integration destination entry S . For example the table generating unit selects Entry 0 having the smallest entry number and the least number of registered polygons that is the number of the polygons corresponding to the area information items.

Next the table generating unit integrates a boundary box indicated in the area information held in the selected entry and a boundary box of a target polygon S . Specifically the table generating unit reads the area information of Polygon 0 a polygon held in Entry 0 and computes a boundary box that is the union of a boundary box of Polygon 0 and a boundary box of Polygon 8 a polygon to be processed.

Next the table generating unit stores again as area information after integration area information indicating the computed boundary box into Entry 0 S .

Furthermore when Polygon 9 is registered the table generating unit selects Entry 1 of which the number of registered polygons is one S and reads area information about registered Polygon 1. Then the table generating unit calculates the union of a boundary box of Polygon 9 and a boundary box of Polygon 1 S and stores again area information that indicates the integrated boundary box and results from the calculation into Entry 1 S .

In other words when a target polygon N is registered the table generating unit calculates the union of a boundary box indicated in area information held in an entry N TMAX and a boundary box of the polygon N and stores again area information that indicates the integrated boundary box and results from the calculation into the entry N TMAX . With this it is possible to hold a lot of area information items about polygons in the area by polygon table having a predetermined fixed capacity.

As stated above when the number of the polygons is greater than the fixed number TMAX the table generating unit divides the polygons into the TMAX number of groups each including at least one polygon. Then the table generating unit calculates for each of the TMAX number of the groups a second area including polygons in the two dimensional plane which are included in the group using the screen coordinates. Next the table generating unit determines from among the divided areas a divided area including at least part of the second area. Next the table generating unit generates the area by polygon table that is a table in which for each group the divided area including the at least part of the second area is associated with the group. In this case the determining unit determines for each divided area a rendering polygon that is among the polygons a polygon included in a group with which a divided area to be processed is associated in the area by polygon table .

More specifically the table generating unit sequentially selects one of the polygons as a target polygon. Then the table generating unit generates for each of the selected target polygons area information about the target polygon and stores the area information into among the entries an entry holding no area information. Moreover when storing area information about a new polygon the table generating unit determines whether the number of area information items stored in the area by polygon table is greater than the fixed number TMAX as the result of storing the area information. When the number of the area information items is greater than the fixed number TMAX the table generating unit calculates using area information stored in a selected entry that is one of the entries and the area information about the new polygon the second area including a new polygon and a polygon that corresponds to the area information stored in the selected entry. Next the table generating unit stores area information indicating a divided area including at least part of the calculated second area into the selected entry.

It is to be noted that although the case is described where the polygon numbers are assigned to the polygons in ascending order of input of the polygons e.g. Polygon 0 Polygon 1 . . . a unique identification number N independent of an input order may be assigned to each polygon. In this case the following processing is performed.

First the table generating unit determines whether an identification number N of a target polygon is greater than TMAX. When the identification number N is less than or equal to TMAX the table generating unit does not perform the integration processing but stores area information about one polygon per entry. For instance the table generating unit stores area information about the target polygon into an entry having an entry number that is the same as the identification number N.

In contrast when the identification number N is greater than TMAX the table generating unit performs the integration processing. For example the table generating unit calculates the union of a boundary box indicated in area information held in an entry N TMAX and a boundary box of the polygon having the identification number N and stores again area information that indicates the integrated boundary box and results from the calculation into the entry N TMAX .

With this it is possible to hold a lot of area information items about polygons in the area by polygon table having a predetermined fixed capacity.

It is to be noted that a method for selecting a storage entry for area information in the integration processing is not limited to the above.

It is also to be noted that in the integration processing the table generating unit may store area information items about polygons consecutive in input order. Hereinafter operations in this case are described.

In the integration processing there is a case where area information items about polygons independent of one another are integrated. This is likely to reduce the accuracy of integrated area information. On the other hand the table generating unit is capable of integrating the area information items about the polygons consecutive in input order that is area information items about polygons of which the display positions are relatively close to each other. This makes it possible to suppress the reduction in accuracy of the integrated area information.

Specifically when the number of polygons is greater than TMAX the table generating unit performs the integration processing such that regarding the exceeding number of the polygons area information items about two consecutive polygons are held in one entry. Moreover when the number of original polygons is greater than TMAX 2 the table generating unit performs the integration processing such that regarding the exceeding number of the original polygons area information items about four consecutive polygons are held in one entry. Furthermore when the number of polygons is greater than TMAX 2 the table generating unit performs the integration processing such that regarding the exceeding number of the polygons area information items about 2consecutive polygons are held in one entry.

Next as shown in the table generating unit calculates a boundary box 0 0 and 1 2 that is the union of a boundary box 0 0 and 1 1 of newly input Polygon 8 a polygon and a boundary box 0 1 and 1 2 of Polygon 9 a polygon that is input next and stores as new area information area information indicating the boundary box into Entry 1. With this the area by polygon table shown in is generated.

In other words when the number of the polygons exceeds the number of the entries the table generating unit merges the content of the registered two entries into one entry calculates the union of area information items about newly input polygons the number of which is the same as the number of mergences that is the number of merged polygons and stores the union into an empty entry. With this even if the number of the polygons is greater than the number of the entries it is possible to hold every area information item.

Furthermore when Polygon 10 is registered in a state shown in since the area information items about the two polygons that are as many as the number of the mergences are already held in Entry 1 the table generating unit selects Entry 2 and Entry 3 as the next entries to be merged. To put it another way the table generating unit selects two entries having the least number of mergences as entries to be merged. Then the table generating unit merges area information items of the selected two entries and stores the merged area information into Entry 2 and area information about new Polygon 10 into Entry 3.

Moreover when Polygon 11 is registered since only the area information about the one polygon is registered in Entry 3 the table generating unit calculates the union of a boundary box of Polygon 10 and a boundary box of Polygon 11 and stores the calculation result into Entry 3.

Furthermore when Polygon 12 is registered since the area information items about the two polygons that are as many as the number of the mergences are held in Entry 3 the table generating unit selects Entry 4 and Entry 5 as the next entries to be merged. Then the table generating unit merges area information items of the selected two entries and stores the merged area information into Entry 4 and area information about new Polygon 12 into Entry 5.

Repeatedly performing the above processing results in storing area information about two polygons in each of all the entries as shown in . When Polygon 16 is further registered in this state the table generating unit reads boundary boxes of Entry 0 and Entry 2 and merges the two read boundary boxes. Then the table generating unit stores the merged area information about four Polygons 0 to 3 into Entry 0 and area information about Polygon 16 into Entry 2 . From this state the table generating unit is capable of storing merged area information about four new Polygons 16 to 19 into Entry 2.

When new Polygons to are registered the table generating unit merges area information items of Entry 4 and Entry 6 to generate merged area information about four Polygons 4 to 7 and stores the merged area information into Entry 4 and area information items about new Polygons 20 to 23 into Entry 6 . When the number of the polygons reaches 24 the merged area information about the four polygons is held in the entry having the entry number of 2 k k 0 1 2 3 and the merged area information about the two polygons is held in the entry having the entry number of 2 k 1.

When Polygon 24 is further registered the table generating unit selects as an entry to be merged the entry 2 k 1 that holds not the merged area information about the four polygons but the merged area information about the two polygons. Stated differently the table generating unit merges the area information items of Entry 1 and Entry 3 to generate merged area information about four Polygons 4 to 7 and stores the merged area information into Entry 1 and area information about Polygon 24 into Entry 3 . From this state the table generating unit is capable of storing merged area information about four Polygons 24 to 27 into Entry 3.

When new Polygons 28 to 31 are registered the table generating unit merges area information items of Entry 5 and Entry 7 to generate merged area information about four Polygons 12 to 15 and stores the merged area information into Entry 5 and area information items about new Polygons 28 to 31 into Entry 7 . In a state shown in the area information items about the four polygons are stored in each of all the entries.

When Polygon 32 is further registered in this state the table generating unit merges the area information items of Entry 0 and Entry 4 to generate merged area information about eight Polygons 0 to 7 and stores the merged area information into Entry 0 and area information about Polygon 32 into Entry 4 .

As stated above when storing area information about a new polygon the table generating unit determines whether the number of area information items stored in the area by polygon table is greater than the fixed number TMAX as the result of storing the area information. When the number of the area information items is greater than the fixed number TMAX the table generating unit calculates using two area information items stored in a first entry and a second entry among entries a second area including a polygon corresponding to the area information stored in the first entry and a polygon corresponding to the area information stored in the second entry. Next the table generating unit stores area information indicating a divided area including at least part of the calculated second area into the first entry and the area information about the new polygon into the second entry.

As just described the table generating unit performs the integration processing so that the results of the merging are arranged in the order of input of the polygons. With this the table generating unit is capable of making the best use of the locality of the polygons and thereby generating the area by polygon table for which a reduction in accuracy is suppressed. The determining unit uses the area by polygon table .

After the area by polygon table is generated after S the rendering region setting unit selects a divided area to be processed from among divided areas S . Since the rasterization is performed for each divided area in the divided area based rendering the rendering region setting unit outputs information indicating a current divided area to be processed.

Hereinafter a case is described where an area ID used by the table generating unit is used as information indicating a divided area. In when the top left divided area is to be processed the rendering region setting unit sets XID YID 0 0 and when the bottom right divided area is to be processed the rendering region setting unit sets XID YID 7 3 . Then the rendering region setting unit transmits to the determining unit an area ID indicating the divided area to be processed.

The command receiving unit B receives a rendering command including a pointer for polygon data . The command receiving unit B fetches a polygon rendering start command and notifies the determining unit of the fetching while the command receiving unit A fetches a polygon rendering start command and notifies the coordinate converting unit of the fetching.

The determining unit determines using the area by polygon table a polygon included in the divided area to be processed S . Specifically the determining unit determines by referring to the area by polygon table whether each polygon is within the divided area to be processed and deletes any polygon determined to be out of the divided area.

Here an order and the number of polygons processed by the coordinate converting unit need to match an order and the number of polygons processed by the determining unit or the numbers of polygons need to match between a time of generating a table and a time of rendering and the same identification numbers need to be assigned to the same polygons between the time of generating a table and the time of rendering. The following describes operations S and S performed by the determining unit and the area rendering unit with reference to a flow chart shown in .

First the determining unit selects a polygon N to be processed S . Specifically the determining unit obtains an area ID XID YID indicating a divided area to be processed and information indicating the polygon N 0 N

Next the determining unit calculates an entry number of an entry included in the area by polygon table and holding area information about the polygon N using a polygon number N indicating a polygon processing order or an identification number N unique to each polygon S . This calculation method depends on the integration processing performed by the table generating unit . For instance the area information about the polygon N is held in the entry N TMAX based on the method described first as the exemplary integration processing. In other words the determining unit determines an entry holding area information about a polygon to be processed according to the procedure of the table generating unit . Specifically the table generating unit sequentially selects polygons as target polygons according to an order of data items of the polygons included in the rendering command . The determining unit associates using the above order the polygons and area information items stored in entries. Alternatively the table generating unit sequentially selects unit polygons as target unit polygons according to unique identification numbers N assigned to polygons included in the rendering command . The determining unit associates using the identification numbers N the polygons and area information items stored in entries.

Next the determining unit obtains the area information about the polygon to be processed from the entry included in the area by polygon table and having the entry number calculated in step S S . Here the area information indicates a two dimensional boundary box and specifically includes the minimum area ID minXID minYID and the maximum area ID maxXID maxYID of the boundary box.

Next the determining unit determines whether the divided area to be processed is within the boundary box S . Specifically when minXID XID maxXID and minYID YID maxYID are satisfied the polygon N is within the divided area to be processed.

Since it is not necessary to rasterize the polygon N when the polygon N is not within the divided area to be processed No in S the determining unit determines not to perform processing on the polygon N and deletes the polygon N S . To put it another way the determining unit excludes the polygon N from a rendering target of the divided area to be processed.

In contrast when the polygon N is within the divided area to be processed Yes in S the determining unit determines that the polygon N is to be rendered since there is a possibility that the polygon N is a target of rasterization and notifies the area rendering unit of the determination S .

Then the area rendering unit performs rendering on the polygon to be rendered SA . Specifically the area rendering unit loads polygon data of the polygon to be rendered and performs vertex processing rasterization and transferring to the final rendering region. Stated differently the area rendering unit loads for the polygon determined to be rendered by the determining unit not only vertex coordinates but also all necessary vertex attributes performs appropriate vertex processing and finally performs rasterization on the divided area.

As stated above the determining unit and the area rendering unit operate in parallel. In other words the determining unit performs determination processing on a subsequent polygon while performing rendering of a polygon.

When the above processing is not performed on all the polygons No in S the next polygon is selected S and step S and the subsequent processing are performed on the selected polygon.

Moreover after rasterizing all the polygons determined to be rendered with respect to the divided areas to be processed the area rendering unit transfers pixel data that is the results of rasterization to memory regions corresponding to the divided areas to be processed in the final rendering region.

When the above processing S to S is not performed on all the divided areas No in S the next divided area is selected S and step S and the subsequent processing are performed on the selected divided area.

As stated above the polygon shape processing unit performs the processing for generation of the area by polygon table only once for one frame scene of a rendering target. Moreover the polygon by area rendering unit performs by referring to the generated area by polygon table the rendering S and S as many times as the number of the divided areas.

As described above the divided area based rendering device according to this embodiment calculates the area information items about the polygons and generates the area by polygon table that is the table in which the area information items are associated with the respective polygons. Then the divided area based rendering device determines by referring to the area by polygon table in the divided area based rendering whether each polygon is within the divided area to be processed. The divided area based rendering device loads the polygon data only for the polygon determined to be within the divided area to be processed and performs the vertex processing the rasterization and the transferring. With this even when a lot of visible polygons are present the divided area based rendering device is capable of performing the divided area based rendering without exceeding the size of the memory region previously reserved. As a result it is possible to greatly reduce the memory bandwidth.

Embodiment 2 describes a modification of the divided area based rendering device according to Embodiment 1.

In the divided area based rendering device shown in the functions of a table generating unit and a table holding unit included in a polygon shape processing unit and a determining unit included in a polygon by area rendering unit are different from those of the table generating unit the table holding unit and the determining unit shown in .

As shown in after coordinate conversion processing S the table generating unit generates an area by polygon table S . Here in table generating processing S the following point differs from Embodiment 1. The table generating unit calculates only for a polygon to which an invalid flag is not added area information and stores the calculated area information into the area by polygon table . In other words the table generating unit does not calculate for a polygon to which an invalid flag is added area information and store the calculated area information into the area by polygon table .

Next the table generating unit generates a polygon attribute table S . Specifically the table generating unit determines a polygon attribute indicating whether each polygon is a valid polygon or an invalid polygon depending on whether the invalid flag is added to the polygon. Then the table generating unit counts using the polygon attribute the number of consecutive polygons having the same polygon attribute and stores a set of the polygon attribute and the number of the consecutive polygons having the same polygon attribute into one entry of the polygon attribute table every time the polygon attribute changes.

Hereinafter operations in step S are described with reference to . Information input from the coordinate converting unit is a set of screen positions of Polygons 0 to 8 and invalid flags. Since no invalid flag is added to Polygons 0 1 6 7 and 8 these polygons are valid polygons and have polygon attributes indicating valid. Since invalid flags are added to Polygons 2 3 4 and 5 these polygons are invalid polygons that are not to be rendered in all divided areas and have polygon attributes indicating invalid.

As shown in the table generating unit calculates only for valid Polygons 0 1 6 7 and 8 area information items and stores the area information items into entries included in the area by polygon table . In contrast the table generating unit does not calculate for invalid Polygons 2 3 4 and 5 area information items and store the area information items into entries.

The table generating unit includes a counter that counts how many same polygon attributes continue and stores a set of attribute information and an attribute count value into one entry of the polygon attribute table 1 every time a polygon attribute changes 2 every time a count value reaches an upper limit value that an attribute counter is capable of holding or 3 when all polygons are processed. Here the attribute information is information indicating an invalid polygon or a valid polygon invalid or valid . The attribute counter indicates the number of polygons consecutively input and having a corresponding polygon attribute.

As stated above the table generating unit counts the numbers of consecutive valid polygons and consecutive invalid polygons among the polygons and generates the polygon attribute table indicating the numbers of the consecutive valid polygons and the consecutive invalid polygons.

In an example shown in when valid Polygons 0 and 1 continue and the polygon attribute changes to invalid Valid 2 is stored into Entry 0 of the polygon attribute table . Next when invalid Polygons 2 3 4 and 5 continue and the polygon attribute changes to valid Invalid 4 is stored into Entry 1 of the polygon attribute table . Then when valid Polygons 6 7 and 8 continue and after all the polygons are processed Valid 3 is stored into Entry 2 of the polygon attribute table .

As seen above by generating the polygon attribute table separately from the area by polygon table it is possible to prevent the entries of the area by polygon table from being used for the area information items about the invalid polygons for which area management is originally unnecessary. Moreover the above described integration processing is prevented from easily occurring by storing the area information items about only the valid polygons into the area by polygon table . This makes it possible to suppress a reduction in accuracy of the area information.

The determining unit determines by referring to the polygon attribute table whether each polygon is to be rendered S . Moreover the determining unit deletes any polygon determined to be not rendered. In other words the determining unit deletes any polygon not to be rendered without depending on a divided area. Specifically the determining unit deletes any polygon to be culled any polygon all the vertices of which are out of a final rendering region due to clipping and so on.

First the determining unit selects the first entry in the polygon attribute table S . Specifically the determining unit initializes to 0 an entry number ENTRYID of an entry to be selected.

Next the determining unit obtains attribute information and an attribute count value from the selected entry ENTRYID 0 S .

Next the determining unit selects a polygon to be processed S . Next the determining unit determines whether the obtained attribute information indicates valid or invalid S .

When the attribute information indicates valid Yes in S the determining unit determines that the polygon to be processed is a valid polygon S . Moreover step S and the subsequent processing shown in are performed only on the polygon determined to be the valid polygon.

In contrast when the attribute information indicates invalid No in S the determining unit determines that the polygon to be processed is an invalid polygon and deletes the polygon at this point S .

Next the determining unit determines whether the attribute count value is 0 S . To put it another way the determining unit determines whether a polygon attribute changes.

When the attribute count value is not 0 No in S the same polygon attribute still continues and thus the determining unit selects the next polygon S and performs step S and the subsequent processing on the selected polygon.

In contrast when the attribute count value is 0 Yes in S and processing is not performed on all valid entries included in the polygon attribute table No in S the polygon attribute changes and the determining unit selects the next entry S . Specifically the determining unit increments ENTRYID by one. Then the determining unit performs step S and the subsequent processing on the newly selected entry.

In contrast when processing is performed on all the entries included in the polygon attribute table in step S the determining unit completes the determination processing S using the polygon attribute table and performs step S and the subsequent processing using the polygons determined to be valid.

As stated above the determining unit determines by referring to the polygon attribute table whether each of the polygons is the valid polygon or the invalid polygon. Next the determining unit determines for each of the divided areas a rendering polygon that is one of the valid polygons which is associated with the divided area by referring to the area by polygon table .

As described above the divided area based rendering device according to this embodiment calculates only the area information items about the valid polygons and stores only the area information items about the valid polygons into the area by polygon table . Moreover the divided area based rendering device stores into the polygon attribute table the number of the consecutive polygons having the same polygon attribute in association with the attribute information indicating valid or invalid. The divided area based rendering device first deletes the invalid polygons by referring to the polygon attribute table when performing the divided area based rendering and then performs the rendering for each divided area by referring to the area by polygon table . Specifically the divided area based rendering device determines whether each polygon is within a divided area to be processed and performs loading of polygon data vertex processing rasterization and transferring only on the polygon determined to be within the divided area.

As stated above the divided area based rendering device does not hold the area information items about the invalid polygons in the area by polygon table . With this the divided area based rendering device is capable of reducing the occurrence of the integration processing when a lot of visible polygons are present and thus suppressing a reduction in accuracy of the area information caused by the integration processing. Moreover as with Embodiment 1 described above the divided area based rendering device is capable of performing the divided area based rendering without exceeding the size of the memory region previously reserved. With this the divided area based rendering device is capable of reducing a memory bandwidth.

Embodiment 1 has described the example where the boundary box is used as the information indicating the divided area to which the polygon belongs. Embodiment 3 describes an example where a boundary bit is used as division information.

Moreover in the example when 1 bit information indicates 1 the 1 bit information indicates that a divided area includes a polygon and when 1 bit information indicates 0 the 1 bit information indicates that a divided area does not include a polygon.

It is to be noted that although the example is described here where the one bit is associated with each divided area one bit may be associated with each unit area including divided areas. The details of the association of the one bit with each unit area are described later.

Hereinafter integration processing when boundary bits are used is described. In the case of using the boundary bits the table generating unit adds two boundary bits to be integrated to compute an integrated boundary bit. In this way it is possible to reduce an amount of computation by using the boundary bits as compared to the case of using the boundary box.

Moreover by using the boundary bits it is possible to prevent a region including a polygon from being set to be unnecessarily large in the integration processing. is a diagram illustrating an exemplary region including polygons and when the integration processing is performed using the boundary boxes in the example shown in . When the two polygons and are disposed apart as shown in the region including the two polygons and is set to be large in the case of using a boundary box. In contrast in the case of using the boundary bits the regions and shown in are directly set as an integrated region including the polygons and . In this way by using the boundary bits it is possible to prevent an unnecessary polygon from being determined to be rendered in rendering of a divided area.

The number of bits of a boundary bit is preferably fixed to a predetermined number of bits. To put it another way the number of the bits of the boundary bit stays constant even when the number of divided areas changes. Hereinafter a case is described where the number of the bits of the boundary bit is fixed to 64 bits of eight vertical bits by eight horizontal bits.

As stated above by fixing the number of the bits of the boundary bit it is possible to suppress an increase in an amount of data of area information. Moreover the table generating unit is capable of generating an area table having a predetermined amount of data without depending on the number of polygons to be rendered and the number of divided areas.

However when divided areas are associated with one bit of the boundary bit the accuracy of setting a region including a polygon decreases as compared to the case of using the boundary box.

As stated above it is possible to set an appropriate region after the integration processing when the boundary bit is used. On the other hand by using the boundary box it is possible to maintain the accuracy of setting a region without depending on the number of divided areas. It is to be noted that although there is a possibility that an amount of data of information indicating a boundary box increases when the number of divided areas increases the increased amount is sufficiently less than an increased amount of data of a boundary bit.

In order to utilize such an advantage of each information each area information included in the area by polygon table may include both a boundary bit and information indicating a boundary box. is a diagram illustrating an exemplary area by polygon table when the area information includes both a boundary bit and information indicating a boundary box.

In step SA the determining unit obtains area information about a polygon to be processed which is included in the area by polygon table . This area information includes a boundary bit and information indicating a boundary box.

Next the determining unit determines whether a divided area to be processed is within the boundary box SA . It is to be noted that specific details of the process are the same as in step S in Embodiment 1.

When the divided area to be processed is within the boundary box Yes in SA the determining unit determines whether the divided area to be processed is within a region indicated by the boundary bit SB . Specifically when 1 bit information corresponding to the divided area to be processed indicates 1 the determining unit determines that the divided area is within the region indicated by the boundary bit and when the 1 bit information corresponding to the divided area to be processed indicates 0 the determining unit determines that the divided area is not within the region indicated by the boundary bit.

When the divided area to be processed is within the region indicated by the boundary bit Yes in SB the determining unit determines that a polygon to be processed is to be rendered S .

In contrast when the divided area to be processed is not within the boundary box No in SA or is not within the region indicated by the boundary bit No in SB the determining unit deletes the polygon to be processed S .

It is to be noted that the order of steps SA and SB may be a different order. For instance step SB may be performed prior to step SA or part of the processes may be performed simultaneously.

As described above the determining unit determines for each divided area a polygon that is one of the polygons which is associated with the divided area in first information indicating a boundary box and with the divided area in a boundary bit second information as a rendering polygon.

With this the divided area based rendering device is capable of setting a more appropriate region after the integration processing and maintaining the accuracy of the setting of the region without depending on the number of the divided areas.

Embodiment 4 describes an example where an area by polygon group table is used in addition to the area by polygon table .

In the divided area based rendering device shown in the functions of a table generating unit and a table holding unit included in a polygon shape processing unit and a determining unit included in a polygon by area rendering unit are different from those of the table generating unit the table holding unit and the determining unit shown in . Steps S and S are added to processing shown in as compared to the processing shown in . Moreover step SA is different from step S.

As shown in after the processing for generation of an area by polygon table S the table generating unit generates an area by polygon group table S .

It is to be noted that when integration processing is performed on polygons each entry may include the number of entries instead of or in addition to the number of the polygons. Here the number of the entries refers to the number of the entries to which the polygons included in the polygon group are assigned in the area by polygon table .

Although only the processing on one polygon group is described below the processing may be performed on polygon groups. Moreover the same processing e.g. integration processing as the above mentioned processing on the polygons may be performed as the processing on the polygon groups.

Although an example is described below where information indicating a boundary box is used as area information as with Embodiment 1 a boundary bit or both of them may be used as with Embodiment 3.

For instance the table generating unit computes by the same method as the integration processing area information a boundary box about the polygon group using area information items about the polygons to included in the polygon group which are included in the area by polygon group table .

It is to be noted that when the boundary bit is used the area information about the polygon group indicates a region obtained by combining regions to including the polygons to .

Next the rendering region setting unit selects a divided area to be processed from among divided areas S .

Next the determining unit determines using the area by polygon group table a polygon group included in the divided area to be processed S . Specifically the determining unit determines by referring to the area by polygon group table whether each polygon group is within the divided area to be processed and deletes any polygon group determined to be out of the divided area.

Hereinafter the determination processing using the area by polygon group table S is described with reference to . is a flow chart for the determination processing using the area by polygon group table S .

First the determining unit selects a polygon group to be processed S . Next the determining unit obtains area information about the polygon group to be processed which is included in the area by polygon group table S .

Next the determining unit determines whether the divided area to be processed is within a region boundary box indicated in the area information S .

When the polygon group to be processed is not within the divided area to be processed No in S the determining unit determines not to perform processing on the polygon group and deletes the polygon group S .

In contrast when the polygon group to be processed is within the divided area to be processed Yes in S the determining unit determines that the polygon group is to be rendered S .

When the above processing is not performed on all polygon groups No in S the next polygon group is selected S and step S and the subsequent processing are performed on the selected polygon group.

When the processing is performed on all the polygon groups Yes in S step SA shown in is performed subsequently.

In step SA the determining unit determines using the area by polygon table a polygon to be rendered that is one of the polygons included in the polygon group determined to be rendered. It is to be noted that this process is the same as step S in Embodiment 1 except for a point that the polygon to be rendered is a polygon included in the polygon group determined to be rendered.

However when data is deleted on a polygon group by polygon group basis in step S shown in it is sometimes impossible to calculate an entry number of an entry holding the area information about the polygon to be processed which is included in the area by polygon table . In response the determining unit is capable of calculating the entry number of the entry holding the area information about the polygon to be processed using the number of the polygons or the number of entries included in the polygon group which is included in the area by polygon group table .

As stated above the table generating unit generates as an area table i the area by polygon group table first area table that is a table in which for each polygon group a divided area including at least part of the first area including the polygon group is associated with the polygon group and ii the area by polygon table second area table that is a table in which for each polygon a divided area including at least part of the first area including the polygon is associated with the polygon.

The determining unit determines for each divided area i the rendering polygon group that is one of the polygon groups which is associated with the divided area by referring to the area by polygon group table and ii the rendering polygon that is among the polygons included in the rendering polygon group a polygon associated with the divided area by referring to the area by polygon table .

The area rendering unit performs for each divided area vertex processing and rasterization on the rendering polygon.

It is to be noted that although the determining unit performs the determination on all the polygons included in the polygon group determined to be rendered after performing the determination on all the polygon groups in the above description the determining unit may perform the determination on polygons included in a polygon group every time the polygon group is determined to be rendered. To put it another way the determining unit may repeatedly perform on a polygon group by polygon group basis the determination on the polygon group and the determination on the polygons included in the polygon group.

As described above the divided area based rendering device is capable of reducing an amount of processing in the determination processing by performing the determination on a polygon by polygon basis after performing the rough determination on a polygon group by polygon group basis.

Although the example is described above where both the area by polygon group table and the area by polygon table are used only the area by polygon group table may be used. Moreover since processing when only the area by polygon group table is used is the same as processing when the polygon is replaced with the polygon group in the description of Embodiment 1 a detailed description thereof is omitted. When only the area by polygon group table is used it is possible to reduce a capacity of the table and an amount of processing in the generation processing but the accuracy of determining a polygon included in a divided area decreases as compared to when only the area by polygon table is used.

Here a unit including one or more polygons is defined as a unit polygon. Stated differently the unit polygon is one polygon or polygon group. In this case it is possible to replace the polygon or polygon group in each of the embodiments with the unit polygon. 

Although the divided area based rendering device according to the embodiments has been described above the present invention is not limited to these embodiments.

Moreover each processing unit included in the divided area based rendering device according to the embodiments is typically realized as an LSI Large Scale Integration that is an integrated circuit. These LSIs may be integrated into individual chips or into a single chip so as to include part or all of the LSIs.

Furthermore circuit integration is not limited to the LSI but may be realized with a dedicated circuit or a general purpose processor. FPGA Field Programmable Gate Array permitting programming after the manufacture of the LSI or a reconfigurable processor which can reconfigure connection or setting of circuit cells in the LSI may be used.

It is to be noted that in the embodiments each structural element may be implemented with dedicated hardware or realized by executing a software program suitable for the structural element. Each structural element may be realized by a program executing unit such as a CPU and a processor reading and executing a software program stored in a recording medium such as a hard disk and a semiconductor memory.

Moreover the present invention may be the program or a non transitory computer readable recording medium on which the program is recorded. In addition it goes without saying that the program can be distributed via a transmission medium such as the Internet.

Furthermore all the numbers used above are exemplary for specifically describing the present invention and the present invention is not limited to these exemplary numerals.

Furthermore the divisions of the functional blocks in the block diagrams are exemplary and the functional blocks may be achieved as one functional block one functional block may be divided into functional blocks or some of the functions may be transferred to another functional block. In addition the functions of functional blocks having similar functions may be processed by single hardware or software in parallel or in a time sharing manner.

Moreover the orders in which the above steps are performed are exemplary for specifically describing the present invention and orders other than the orders may be used. In addition some of the steps may be performed at the same time as in parallel with other steps.

Although the divided area based rendering device according to one or more aspects has been described above based on the embodiments the present invention is not limited to these embodiments. Those skilled in the art will readily appreciate that various modifications may be made in the embodiments and that other embodiments may be obtained by combining the structural elements in the different embodiments without departing from the spirit of the present invention. Accordingly all such modifications and embodiments may be included in the scope of the one or more aspects.

The present invention is useful as a graphics display system used for embedded devices of which the memory efficiency and the bandwidth efficiency are required. For instance the present invention can be applied to cellular phones televisions and so on.

