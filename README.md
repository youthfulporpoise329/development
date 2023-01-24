# Development

### Link to Deployed Website
If you used the stencil code, this is `https://<your GitHub username>.github.io/<name of your repository>`

### Goal and Value of the Application

The goal of this application is to be a simple bakery website used for online ordering. Each item sold in my bakery is classified as either a bread, cake, pastry, or pie, and is flagged with dietary restrictions such as gluten-free, nut-free, and dairy-free. These items can then be filtered by type and by dietary restriction, and these filters can be combined (so, for example, a user can chose to display only gluten-free pastries). I also implemented the ability to sort the items in my bakery by alphabetical order of their names, by numerical order by their price, or by their type (showing all breads, then all cakes, then pastries, then pies). This sorting functionality also works on its own or in combination with any of the filter options. Lastly, the user is able to add items from my bakery to a cart, which will display the total cost of all the items in the cart, as well as a list of items in the cart next to the quantity of each item. Items can be removed from the cart using remove buttons next to each cart item, which decrease the quantity of that item by one, or remove the item from the cart entirely if there is only one of that item remaining.

### Usability Principles Considered

### Organization of Components

I created a reusable component to be used to represent each bakery item (BakeryItem.js). This component represents each bakery item as a card which displays an image of the item next to info such as the item's name, price, type (bread, cake, pastry, or pie), dietary restrictions (gluten-free, dairy-free, and/or nut-free), and a description of the item. Each cart also has a button allowing you to add the item to your cart. 

I also used a component for the Navigation Bar (Navbar.js). Although this site only has one page and therefore does not require a nav bar to navigate the site, I used this component because I wanted to make the header sticky. 

The rest of the page is contained wholly in App.js. 

### How Data is Passed Down Through Components

Data about each item sold in the bakery is contained in a JSON file, which is then imported into App.js. App.js makes use of a number of filtering and sorting functions to display only the items designated by the selected filters and display them in the correct order as designated by the selected sort. 

Javascript's map() function is then used to map each of the filtered items to its own BakeryItem component, and the info for each of the filtered items is passed to the BakeryItem component through props. 

### How the User Triggers State Changes

If the user chooses to sort the bakery items by name, price, or type, I used React's useState() function to create a constant selectedSort, along with a corresponding function setSelectedSortOption(). I also wrote my own function, sortItems(). Upon the user selecting a sort option, another function, sortItemsEvent() will be called, which takes in the sort event and uses setSelectedSortOption() to designate the selectedSort to be whichever of the three sorting options the user chose, and then calls the sortItems() function. This function makes use of Javascript's sort() function to sort the items by either name, price, or type, and then uses setFilteredItems to return the correctly sorted array. 

If the user filters by dietary restriction or by item type, React's useState() functions create constants selectedRestrictions and selectedTypes, and functions setSelectedRestrictions()

FINISH 

