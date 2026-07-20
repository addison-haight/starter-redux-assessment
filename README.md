# Starter redux assessment: Doggiegram

This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

## Available scripts

In the project directory, you can run the following commands:

### `npm install`

Installs the project dependencies, including Redux packages such as @reduxjs/toolkit and react-redux.

### `npm run dev`

Runs the React app in the development mode.\
Open [http://localhost:3000](http://localhost:3000) to view it in your browser.

Runs an Express API at `http://localhost:3004` that exposes a single endpoint, `GET /api/suggestion`, which returns a dog suggestion at random.

The page will reload when you make changes.\
You may also see any lint errors in the console.

### `npm test`

Runs the test suites.

------------------------------
# Post-assignment questions

1. Describe the biggest challenge you faced when implementing the Favorite Like/Toggle logic and explain the approach you used to solve it.
   - The Favorite toggle did not present any particular challenges and seemed pretty straight forward the way it was established in the starter code. Each of the items in the photos.data.js file already had a tag for isFavorite: false already, so I needed to establish a handler to change the value to True and back when a button is clicked. I went with an event handler on the button to toggle back and forth on the image.
     ``` <button 
          data-testid={`${id}-favorite-button`}
          onClick={() => handleToggleFavorite(id)}>
            {isFavorite ? 'Favorited' : 'Favorite' }
          </button> 

2. Explain how you designed and implemented the Redux store for this project. What state did you choose to centralize, and why?
   - The store used three slices for this project, photos, search and suggestion -- each had its own state. Components were organized by the features in the starter code and I thought this was a good way to keep the code organized. 

3. Explain one key technical decision you made during your implementation. Why did you choose this approach over other possible solutions?
   - For the addPhoto reducer, I decided to go with using the .reduce() method. When I tried to use the state.photos.length + 1 as we had in a previous lesson, I ran into some issues with the ids of photos that remained if any photos were deleted. I did some research on why this might be happening, so looked for other methods that might make the functionality cleaner and not run into bugs if I was deleting photos, so decided to use the .reduct() method. 

4. AI use disclosure: Did you use any AI tools at any stage while preparing or developing this assessment? Yes / No—If yes, briefly describe how you used them responsibly.
   - I used Claude to help with some understanding of new concepts that I had not learned in previous modules, specfically the .reduce() and .unshift() methods. These were new concepts, so I ran through some examples with Claude in order to get a good understanding of the concepts and how to use each and the benefits of these of these methods in order to setup my reducers in the photos.slice.js file. I had previously practice with .splice() and .findIndex(), so I knew I needed a different method to for the toggleFavorite and addPhoto actions.
