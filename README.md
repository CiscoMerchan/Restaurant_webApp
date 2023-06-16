# Getting Started with Create React App

This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

## Available Scripts

In the project directory, you can run:

### `npm start`

Runs the app in the development mode.\
Open [http://localhost:3000](http://localhost:3000) to view it in your browser.

The page will reload when you make changes.\
You may also see any lint errors in the console.

### `npm test`

Launches the test runner in the interactive watch mode.\
See the section about [running tests](https://facebook.github.io/create-react-app/docs/running-tests) for more information.

### `npm run build`

Builds the app for production to the `build` folder.\
It correctly bundles React in production mode and optimizes the build for the best performance.

The build is minified and the filenames include the hashes.\
Your app is ready to be deployed!

See the section about [deployment](https://facebook.github.io/create-react-app/docs/deployment) for more information.

### `npm run eject`

**Note: this is a one-way operation. Once you `eject`, you can't go back!**

If you aren't satisfied with the build tool and configuration choices, you can `eject` at any time. This command will remove the single build dependency from your project.

Instead, it will copy all the configuration files and the transitive dependencies (webpack, Babel, ESLint, etc) right into your project so you have full control over them. All of the commands except `eject` will still work, but they will point to the copied scripts so you can tweak them. At this point you're on your own.

You don't have to ever use `eject`. The curated feature set is suitable for small and middle deployments, and you shouldn't feel obligated to use this feature. However we understand that this tool wouldn't be useful if you couldn't customize it when you are ready for it.

## Learn More

You can learn more in the [Create React App documentation](https://facebook.github.io/create-react-app/docs/getting-started).

To learn React, check out the [React documentation](https://reactjs.org/).

### Code Splitting

This section has moved here: [https://facebook.github.io/create-react-app/docs/code-splitting](https://facebook.github.io/create-react-app/docs/code-splitting)

### Analyzing the Bundle Size

This section has moved here: [https://facebook.github.io/create-react-app/docs/analyzing-the-bundle-size](https://facebook.github.io/create-react-app/docs/analyzing-the-bundle-size)

### Making a Progressive Web App

This section has moved here: [https://facebook.github.io/create-react-app/docs/making-a-progressive-web-app](https://facebook.github.io/create-react-app/docs/making-a-progressive-web-app)

### Advanced Configuration

This section has moved here: [https://facebook.github.io/create-react-app/docs/advanced-configuration](https://facebook.github.io/create-react-app/docs/advanced-configuration)

### Deployment

This section has moved here: [https://facebook.github.io/create-react-app/docs/deployment](https://facebook.github.io/create-react-app/docs/deployment)

### `npm run build` fails to minify

This section has moved here: [https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify](https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify)

#################################################################

1. Delete `src` file. and recreate a newone

2. create `index.js`

3. create `App.js` file
    using 'ES7 React/Redux/React-Native/JS Snippets' to create code more quick like using `rafce` snippets to create components 
    for more    SNIPPETS : `https://github.com/ults-io/vscode-react-javascript-snippets/blob/HEAD/docs/Snippets.md`

4. install dependencies:
 *   `npm install react-icons`

5. base of `src` folder and files like are premade just the base.

6. Navbar component

### Navbar
 1. ```
 import {GiHamburgerMenu} from 'react-icons/gi';
import {MdOutlineRestaurantMenu} from 'react-icons/md';
import images from '../../constants/images'
 ```.

* highlight **Open and Close hamburger menu**:


 ```
 const [toggleMenu, setToggleMenu] = useState(false);

  return( ...

   <div className='app__navbar-smallscreen'>
      <GiHamburgerMenu color='#fff' fontSize={27} onClick={() => setToggleMenu(true)} />
      
      {toggleMenu &&(
        <div className='app__navbar-smallscreen_overlay flex__center slide-bottom'>
          <MdOutlineRestaurantMenu className='overlay__close' fontSize={27} onClick={() => setToggleMenu(false)} />
          <ul className='app__navbar-smallscreen_links'>
            <li className='p__opensans'><a href='#home'>Home</a></li>
            <li className='p__opensans'><a href='#about'>About</a></li>
            <li className='p__opensans'><a href='#menu'>Menu</a></li>
            <li className='p__opensans'><a href='#awards'>Awards</a></li>
            <li className='p__opensans'><a href='#contact'>Contact</a></li>
         </ul>  
        </div>
      )}
 ```