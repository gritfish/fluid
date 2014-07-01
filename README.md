Fluid
=====

What is Fluid?
-----

The Fluid grid framework is responsive grid library that allows for not only nesting grids, but creation of new responsive grids at any size. With a few lines of code, the framework generates all the styles necessary for a completely custom grid layout.

It's the fastest way to get building with grids. You can create a completely new responsive grid system in just a few lines of code.  Don't know less? Fluid comes with 960 grid templates as standard. Just drop the fluid.css file in your project and go.

The fluid grid has a few distinct advantages over other grid systems:
 - A combination of "columns" (divs without margins) and "boxes" (divs with margins) allows not only for unlimited nesting, but dividing the page into sections as well.
 - Multiple grids on the one page. Need more more than one grid? Fluid can handle it. Every section of your website can have its own grid system. They don't even need to be the same width!
 - A mix of percentage and fixed width columns allows for the quick creation of elements with a table-like layout. Need columns that are still a quarter on mobile? Fluid can do it.

How to install
-----

__Using CSS:__ Include the fluid.css file in your html. The default css file comes with 960px 12 and 16 column grids included, as well as fullWidth, half, third and quarter width columns.

__Using LESS:__ include the fluid.less file in your project - to add new grid sizes, see the "extending" section.

__The HTML:__ There's several basic templates in the examples folder to get you started.


How to use Fluid
-----

__Generating your own grids:__ There are two major functions in the LESS that are used to add a grid type:

`.generate(NUMBER_OF_COLUMNS,COLUMN_WIDTH,GUTTER_WIDTH,DIVIDE);`

`.mobileGridReset;`

The code below creates a seven column grid, as well as its small screen and mobile adaptations:

	.gridContainer.seven{
		.setGridContainerWidth(7,110px,30px);
		.generate(7,110px,30px);
	}
	@media (max-width: 980px) {
		.gridContainer.seven{
			.setGridContainerWidth(7,80px,20px);
			.generate(7,80px,20px);
		}
	}
	@media (max-width: 720px) {
		.gridContainer.seven{
			.mobileGridReset;
		}
	}


Most of the time, you won't need the "DIVIDE" parameter. It's there so you can "scale down" a grid to a smaller number of columns. For example `.generate(12,60px,20px,4);` will actually generate a THREE column grid, where `colwide2` is one column, and `colwide6` is two columns wide.