# Character Gallery Viewer

The **Character Gallery Viewer** is a Vue-based application designed to showcase characters from the *Rick and Morty* show. It fetches data from the open API provided by [Rick and Morty API](https://rickandmortyapi.com/) and showcases each character's thumbnail, name, status, creation time, and location. Additionally, the gallery also implements an infinite scrolling feature, loading more characters as the user scrolls down.

![rnm-github-preview — сделано в Clipchamp](https://github.com/madwizz/rnm-api-vue3/assets/101938387/29a5d1d9-7aef-4c52-9a82-42ef776e80fa)


## Structure

The application consists of three main components:

- **App.vue**
- **CharacterGallery.vue**
- **CharacterCard.vue**

### App.vue

- **Components Used**: `CharacterGallery`
- **Template Structure**: The main page container wrapping the `CharacterGallery` component.

### CharacterGallery.vue

- **Components Used**: `CharacterCard`
  
- **Data Properties**:
  - `characters`: An array to hold the fetched characters.
  - `currentPage`: A number denoting the current page of data being fetched.
  - `totalPages`: The total number of pages available from the API.
    
- **Methods**:
  - `getCharacters()`: Fetches characters based on the current page.
  - `onScroll()`: Checks the scroll position and triggers more data loading if needed.
  - `loadMore()`: Increments the current page and fetches more characters.
    
- **Lifecycle Hooks**:
  - `created()`: Invoked when the component is created. Fetches the initial set of characters and adds a scroll event listener.
  - `beforeDestroy()`: Removes the scroll event listener before the component is destroyed.

### CharacterCard.vue

- **Props**: 
  - `character`: An object containing details of the character.
  
- **Template Structure**: A card layout displaying the character's image, name, status, creation date, and location.

## Styling

The styling for the application is achieved using a mix of pure CSS and SCSS. Responsiveness is ensured across various screen sizes by adjusting the column count for the gallery based on the viewport width.

## Requirements Check

- [x] Utilize Vue, preferably version 3 `"vue": "^3.3.4"`
- [x] Ensure it's responsive to various screen sizes: contains media queries that adjust the gallery's column count based on screen width.
- [x] Styling using Tailwind CSS, pure CSS, SCSS, or SASS: The code leverages pure CSS and SCSS.
- [x] Use the open API provided by [Rick and Morty API](https://rickandmortyapi.com/): Data is fetched from this API.
- [x] Each gallery item displays thumbnail, name, status, creation time, and location.

## Installation Guide

### Prerequisites

Before starting the installation process, make sure you have the following tools installed:

- [Node.js](https://nodejs.org/)
- [npm](https://www.npmjs.com/) (comes bundled with Node.js)

### Steps

1. **Clone the Repository**
   
   ```bash
   git clone https://github.com/your-username/rick-and-morty-gallery.git

2. **Navigate to the project directory:**
   
   ```bash
   cd rick-and-morty-gallery
   
3. **nstall dependencies:**
   
   ```bash
   npm install

3. **Run the Project Locally.**
   
   ```bash
   npm run dev

