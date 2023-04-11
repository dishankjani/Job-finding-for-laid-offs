# Assignment 3

* *Date Created*: 31 March 2023

* *Last Modification Date*: 05 April 2023

* *Deployed Application URL*: <https://reboundr.netlify.app>
* *Deployed Application backend*: <https://reboundr-backend.onrender.com>

## Authors

* [Naqeebali Shamsi](@shamsi)        [nq957544@dal.ca] - B00936464
* [Riya Intwala](@intwala)           [ry638970@dal.ca] - B00936464
* [Anirudh Hosur](@hosur)            [an516658@dal.ca] - B00936464
* [Dishank Jani](@djjani)            [ds999989@dal.ca] - B00917756
* [Mounisha Soudaboina](@soudaboina) [mn660371@dal.ca] - B00936464
* [Alis Mangukiya](@alis)            [al819067@dal.ca] - B00936464

## Getting Started

### Prerequisites

To have a local copy of this lab / assignment / project up and running on your local machine, you will first need to install the following software/libraries / plug-ins

* `Node.js`

See the following section for detailed step-by-step instructions on how to install this software / libraries / plug-ins

### Installing

Firstly install Node.js from the following link:

`https://nodejs.org/en/download/`

After installing, clone the git repository and switch to the **main** branch

Open the command prompt and run the following commands:

```bash
> npm install
> npm run dev
```

Now, you'll need environment variables for the application to work locally. Contact the [author](#authors) for the more information.

## Deployment

Created a new app on netlify website and make modifications to code. Upon pushing the code to branch, it'll be automatically deployed using the CI/CD pipeline created.

Refer to following .gitlab.yml file for CI/CD deployment code:

`https://git.cs.dal.ca/shamsi/group9_reboundr/-/blob/naqeebali_shamsi_B00936464/frontend/.gitlab-ci.yml`

## Built With

* [Node.js](https://nodejs.org/en/) - JavaScript runtime environment

* [Express](https://expressjs.com/) - Web framework for NodeJS

* [Material UI](https://mui.com/) - React component library

## Sources Used

### For Deployment on Netlify

To deploy on Netlify, the api code must be deployed as serverless functions. I followed multiple video tutorials on YouTube and used information from each of them to deploy my api server on Netlify. Following are the tutorials that I referred to:

* [AniaKubow](https://www.youtube.com/watch?v=n_KASTN0gUE)

* [asyncfilebybibek](https://www.youtube.com/watch?v=q1TrsvKdpcU)

### For deployment on Render

I cloned the backend part of our application to a private github repository. It can be connected with the Render platform with a few clicks and Render automatically picks up the latest commit from the specified branch (specified during setup).

### src/RegistrationPage.js

```javascript
 const handleSubmit = (event) => {
    event.preventDefault();
    const data = new FormData(event.currentTarget)
    setFormData(data);
    navigate('/profile');

  };
```

The code snippet above uses FormData to get an object consisting of all the inputs in the form present in the registration page.
It was inspired by the solution given by [Mayank Shukla](https://stackoverflow.com/users/5185595/mayank-shukla). His code snippet:

```javascript
let formData = new FormData();    //formdata object

formData.append('name', 'ABC');   //append the values with key, value pair
formData.append('age', 20);

const config = {     
    headers: { 'content-type': 'multipart/form-data' }
}

axios.post(url, formData, config)
    .then(response => {
        console.log(response);
    })
    .catch(error => {
        console.log(error);
    });
```

- There is no modification of the OP's code in this case. My code is original and is only inspired by the OP's work.

### src/UserContext.js

```javascript
import  { createContext } from "react";

const UserContext = createContext({
  user: "",
  setUser: () => {}
});
export default UserContext;

```

The code above was inspired by the solution written by [Divyanshu Maithani](https://stackoverflow.com/users/4952669/divyanshu-maithani) as shown below:

```javascript
import React, { Component } from "react";
import ReactDOM from "react-dom";

import LanguageContext from "./language-context";
import LanguageSwitcher from "./LanguageSwitcher";

class App extends Component {
  setLanguage = language => {
    this.setState({ language });
  };

  state = {
    language: "en",
    setLanguage: this.setLanguage
  };

  render() {
    return (
      <LanguageContext.Provider value={this.state}>
        <h2>Current Language: {this.state.language}</h2>
        <p>Click button to change to jp</p>
        <div>
          {/* Can be nested */}
          <LanguageSwitcher />
        </div>
      </LanguageContext.Provider>
    );
  }
}

const rootElement = document.getElementById("root");
ReactDOM.render(<App />, rootElement);


```

: There is no modification of the OP's code in this case. My code is original and is only inspired by the OP's work.

### Email validation regex - /validations.js

```javascript
const pattern = "[a-z0-9!#$%&'*+/=?^_`{|}~-]+(?:\.[a-z0-9!#$%&'*+/=?^_`{|}~-]+)*@(?:[a-z0-9](?:[a-z0-9-]*[a-z0-9])?\.)+[a-z0-9](?:[a-z0-9-]*[a-z0-9])?";
const validEmailRegex = RegExp(pattern);
```

The regex above is from an unknown author. It conforms to the RFC822 standard and was posted on [regexr](https://regexr.com/2rhq7)

* It was taken as is without any modification.

### src/*.js

The following components from Material-UI were used and modified:

```list
1. Typography - Used for Titles/headings/text
2. Box - Used for creating layouts
3. Grid - Used for creating layouts
4. Button - Used to render buttons for form-actions
5. Rating - Used to render rating stars
6. LinearProgress - Used to render a linear progress bar
7. Autocomplete - Used to render a normal text input enhanced by a panel of suggested options.
8. Tooltip - Used to render a toolitp
9. Paper - Used to render a background resembling a sheet of paper
```

### Authentication and session management

Inspired from the [article](https://medium.com/swlh/set-up-an-express-js-app-with-passport-js-and-mongodb-for-password-authentication-6ea05d95335c) by [Fabian Bosler](https://medium.com/@fabianbosler)

## Acknowledgments  

* [ExpressJS tutorial](https://dal.brightspace.com/d2l/le/content/250793/viewContent/3445551/View) by [Gurleen Saluja] for guiding how to create first NodeJS application.
* [Node, Express, MongoDB & SQL II](https://dal.brightspace.com/d2l/le/content/250793/viewContent/3445566/View) by [Mugdha Agharkar] for guidance on completing this tutorial.
* [React documentation](https://reactjs.org/docs/create-a-new-react-app.html) for guiding how to create first react application
* [Material UI](https://mui.com/) for providing better UI components
* The Professor and all the TAs of this course
