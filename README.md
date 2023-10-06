# Overview:
  The Character Gallery Viewer is a Vue-based application designed to display characters from the Rick and Morty show. It fetches data from the open API provided by https://rickandmortyapi.com/ and showcases each character's thumbnail, name, status, creation time, and location. The gallery also implements an infinite scrolling feature, loading more characters as the user scrolls down.

# Structure:
  The application consists of three main components:

## App.vue - This is the root component that encompasses the entire application.
## CharacterGallery.vue - This component fetches characters from the API and displays them using the CharacterCard component. It is also responsible for the infinite scrolling feature.
## CharacterCard.vue - This component presents individual character details based on the passed-in character prop.

# Component Breakdown:

## App.vue:

  Components Used: CharacterGallery
  Template Structure: The main page container wrapping the CharacterGallery component.

## CharacterGallery.vue:

  Components Used: CharacterCard
  
  Data Properties:
    characters: An array to hold the fetched characters.
    currentPage: A number denoting the current page of data being fetched.
    totalPages: The total number of pages available from the API.
    
  Methods:
    getCharacters(): Fetches characters based on the current page.
    onScroll(): Checks the scroll position and triggers more data loading if needed.
    loadMore(): Increments the current page and fetches more characters.
    
  Lifecycle Hooks:
    created(): Invoked when the component is created. Fetches the initial set of characters and adds a scroll event listener.
    beforeDestroy(): Removes the scroll event listener before the component is destroyed.

## CharacterCard.vue:

  Props: character: An object containing details of the character.
  
  Template Structure: A card layout displaying the character's image, name, status, creation date, and location.
  
  Styling: The styling for the application is achieved using a combination of pure CSS and SCSS.
  
  It ensures responsiveness across various screen sizes, adjusting the column count for the gallery based on the viewport width.

## Requirements Check:

✔️Utilize Vue, preferably version 3 "vue": "^3.3.4"
✔️Focus less on design but ensure it's responsive to various screen sizes: the code contains media queries that adjust the gallery's column count based on screen width.
✔️Styling using Tailwind CSS, pure CSS, SCSS, or SASS: The code uses pure CSS and SCSS for styling.
✔️Use the open API provided by https://rickandmortyapi.com/: the CharacterGallery component fetches data from this API.
✔️Each gallery item includes thumbnail, name, status, creation time, and location: all these elements are present in the CharacterCard component.
