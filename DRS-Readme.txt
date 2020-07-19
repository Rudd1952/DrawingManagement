2020-07-19
Drawing Retrieval System proof of concept published on restricted web site.
The stystem is now fully operational but restricted to limited source material available to SpaceWorx.

The system concept is to allow for a visual search of drawings once a filtering exercise has been carried out on the full repository.  A compact image of the Original PDF is stored in the web site to speed up response, this image is active and clicking on it will open a second window with the original PDF file.  This PDF file can then be re-saved locally for distribution to project teams if necessary.  The original PDF file remains on the server.  The system can work with DWG files to launch AutoCAD or any other installed Dwg viewer application.
The files can be stored on the server to limit storage requirements on the Web or to enable other searches, editing or greater security.  It is proposed that the files are stored in a directory structure that follows\University\Campus\Building.  Sub-directories by  specialist or discipline are possible where there are a lot of drawings. Drawings can also be moved into Archive folders to take them out of the filter process.  The system can be extended for other file formats such as Revit, Excel or Word.
Security will be enabled at a network level by restricting access to the Web Site.  The Objective is to make Reference and current drawings available to Facilities Management staff from any point of the campus with either a PC or Mobile device.

2020-06-19
Drawing Retrieval System current status

- The navigation bar is moved to the top of the page as a permanent position. Previously was a 'sticky' which has known issues with some browsers
- The menu items in the navbar have Campus and Buildings which basically do the same thing
- Drawing Types in the navbar are there just as a reminder of what types of catagories the drawings could be organised - all disabled at this stage
- The About menu opens this file (for now to explain changes in the system) in future to be more informative.
- Contact and the Search input box are still for future

- Client logo and title for branding and reference

- The Drawing Retrieval paragraph and image are for brief explaination of system and aesthetic - learn mere button for future

- Selecting a building in the menu populates the Floor, Discipline and Subject lists on the left side of the working interface. Updates the heading to state the building being reviewed

- Floor Listing - lists all the floor in groups with number of drawings in each group. Sorted by floor number regardless of the naming of the floor in the list.
- Upper level floors first then basements, then roof drawings.

- Discipline Listing - list grouped with number of drawings for each group, alphabetically ordered.

- Subject Listing - list grouped with number of drawings for each group, alphabetically ordered.

- The details on the right side of the working area have all been made consistent and if the drawing had a CAD file associated with it, the file can be opened in CAD program. The original CAD file cannot be modified from here, a copy is made in a temporary folder and can be saved elsewhere if modified.

- Current XML Record structure
	<Drawings>
		<DrawingNumber>-</DrawingNumber>			The drawing number on the drawing in the title block
		<DrawingTitle>-</DrawingTitle>				The description of the drawing in the title block
		<DrawingDescription>-</DrawingDescription>	Normalised description of drawing title
		<Scale>-</Scale>							The scale of the drawing as stated in the title block
		<RevisionNumber>-</RevisionNumber>			The latest revision number of the drawing
		<Consultant>-</Consultant>					Name of consultant or practice that produced documentation
		<Building>-</Building>						The building name or reference as it is currently known
		<BuildingAB>-</BuildingAB>					As-built reference to building on the drawing
		<Floor>-</Floor>							The floor reference of the drawing
		<FloorID>-</FloorID>						Floor Sequence Number e.g. 00=Ground, 01=First, B1=Basement 1, L1=Level 1
		<Discipline>-</Discipline>					Engineering discipline of the drawing
		<Site>-</Site>								Campus reference of the drawing
		<DWGFile>-</DWGFile>						The CAD filename of the drawing
		<DWGLocation>-</DWGLocation>				Path to DWG file
		<PDFFile>-</PDFFile>						PDF Filename
		<PDFLocation>-</PDFLocation>				Path to PDF file
		<JPGFile>-</JPGFile>						JPG Filename
		<JPGLocation>-</JPGLocation>				Path to JPG file
		<Subject>-</Subject>						Document subject
		<FileLocation>-</FileLocation>				Path to capture file
	</Drawings>
	
- Due to the different ways of handling XML files over HTTP this system does not work with Internet Explorer and Microsoft Edge Legacy at this stage. It does work with Chrome, FireFox and Microsift Edge Insider (Dev).
