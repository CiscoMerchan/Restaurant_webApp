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

<br>

### Heading

1. Create div to subdivide the content. in this case there is to main div inside Header component one is the text and the other is the image.

on the text div import the `SubHeading ` component in component folder. 

**TIP Note**  to import a component: write the name the component <MyComponent />, doble click in the text and `Ctrl + spacebar` the name of the file to import will be display `Enter` and that will import the file at the top of the folder.

### About Us

**TIP Note**  to go to the component file , click on the component `Ctrl+Click` and that will open the component folder clicked. 



### Special Menu

    Reusing components and using .map() to render data. 

### Chef

be more mindful about how works with divs

### Intro Video

`useRef()` hook ( more info : `https://dmitripavlutin.com/react-useref/`)


### Laurels

**TIP NOTE** Is very important to remember that any css selector and rules that repete along the webapp like "Subheading" or "titles" better set those rule in the App.css or a index.css, like this using while styling the components without repeating the css code every time. 

** If it is necessary to create a several"cards" that can be render with .map() (better do it as a children component) create a component out side of the component and in the same file becase it is just for that particular parent component. example: 

```
// CHILDREN COMPONENT
const AwardCard = ({ award: {imgUrl, title , subtitle }}) => (
  <div className='app__laurels_awards-card'>
    <img src={imgUrl} alt='award'/>
    <div className='app__laurels_awards-card_content'>
      <p className='p__cormorant' style={{ color: '#DCCA87'}}>{title}</p> 
      <p className='p__cormorant'>{subtitle}</p> 
    </div>
  </div>
)

// PARENT COMPONENT
const Laurels = () => (
  <div className="app__bg app__wrapper section__padding" id="awards">

    <div className='app__wrapper_info'>
      <SubHeading title="Awards & recognition" />
      <h1 className='headtext__cormorant'>Our Laurels</h1>

      <div className='app__laurels_awards'>
        {data.awards.map((award) => 
        <AwardCard
          award={award}
          key={award.title}
         />
          )}
      </div>     
    </div>
    
    <div className='app__wrapper_img'>
        <img src={images.laurels} alt='laurels' />  
    </div>
           
  </div>
);

export default Laurels;

```

### Gallery

Tocreate a gallery

 
  `const galleryImages = [images.gallery01, images.gallery02, images.gallery03, images.gallery04]
  
  const scrollRef = React.useRef(null);

  const scroll = (direction) => {
    const { current } = scrollRef;

    if(direction === 'left') {
      current.scrollLeft -= 300;
      } else {
        current.scrollLeft += 300;
      }
  } `

` <div className='app__gallery-images'>
      <div className='app__gallery-images_container' ref={scrollRef}>
        {galleryImages.map((gImg,index) => ( 
          <div className='app__gallery-images_card flex__center' key={`gallery_image-${index+1}`}>
          <img src={gImg} alt='gallery image' />
          <BsInstagram className='gallery__image-icon' />
          </div>
        
        ))}
      </div>
      <div className='app__gallery-images_arrow'>
        <BsArrowLeftShort className='gallery__arrow-icon' onClick={() => scroll('left')} />
        <BsArrowRightShort className='gallery__arrow-icon' onClick={() => scroll ('right')} />
      </div>
    </div>
    
  </div> `

  ###FindUs

  using css selector from App.css and inline css 