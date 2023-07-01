To use express-generator: navigate to path where you want to folder to be

express <name_of_project> --view=<pug|ejs|erb>

$ cd into directory
$ npm install

run the app: (DEBUG=<name> sets the enviornment variable to point the debugger to the project. You could just use npm start)  
DEBUG=express-locallibrary-tutorial:* npm start

as far as nodemon is concerned, under scripts in package.json 

"scripts": {
    "devstart": "nodemon ./bin/www",
}

npm run devstart



controller use express-async-handler. While qurying the db it needs a way to error check and try/catch would take a lot of real estate


FROM THIS: 

exports.get("/about", function (req, res, next) {
  try {
    const successfulResult = await About.find({}).exec();
    res.render("about_view", { title: "About", list: successfulResult });
  }
  catch (error) {
    return next(error);
  }
};


TO THIS: 

// Import the module
const asyncHandler = require("express-async-handler");

exports.get(
  "/about",
  asyncHandler(async (req, res, next) => {
    const successfulResult = await About.find({}).exec();
    res.render("about_view", { title: "About", list: successfulResult });
  })
);
