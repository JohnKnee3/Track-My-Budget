# 19.1.6

Went to the Dev tools and learned how we can go to the Network tab to adjust the internet speed. In the spot up top where it says no throttling we instead select Slow 3g.
First Meangful paint is gone a we should use Largest Contentiful Paint instead.

# 19.1.7

We used https://javascript-minifier.com/ to reduce the white space in our code. We used https://imagecompressor.com/ to reduce the image size of 6 of our jpg images. Finally we added defer

<script src='assets/js/vendor/jQuery.js' defer ></script>
<script src='assets/js/vendor/bootstrap.js' defer ></script>
<script src='./dist/script.min.js' defer ></script>

to lazy load our js files to only be used when needed.

# 19.2.4

Downloaded the webpack npm package.

# 19.2.5

We built the webpack.config.js file that looks like this.

<!-- const webpack = require("webpack");
const path = require("path");
module.exports = {
entry: "./assets/js/script.js",
output: {
path: path.resolve(\_\_dirname, "dist"),
filename: "main.bundle.js",
},
plugins: [
new webpack.ProvidePlugin({
$: "jquery",
jQuery: "jquery",
}),
],
mode: "development",
}; -->

This goes through and bundles up all of our scrpit.js files and compresses it so it will run faster. We had to require Jquery(in this file) and bootstrap(in script.js) to get the page to perform properly. This went very fast and may need a re read.

# 19.3.4

We went through the process of splitting our code from the script.js into several different files so they will only be loaded when needed. There was a ton of copy paste and some things don't quite feel right. I will have to pay close attention moving forward to see if this works because we have not tested anything yet.

# 19.3.5

We set up the files and got the build to run. There were several issues along the way but one of the biggest things we updated was our webpack file. We added

output: {
filename: "[name].bundle.js",
path: path.resolve(\_\_dirname, "dist"),
},

the [name] bit so it would create a file named correctly each time. For whatever reason path: \_\_dirname + '/dist' would never work for me but path: path.resolve(\*\*dirname, "dist") does.

# 19.3.6

We were introduced to more webpack functionality. This time we were intorduced to file-loader & image-webpack-loader. These two things together made it possible to load images into the dist folder and then resizes so the app can perform better.
