How to run
Install Gulp - npm install -g gulp
npm install to install dependencies.
Run gulp build-all to build the code.
Run gulp nodemon to start the server.
Go to http://localhost:9080/
You can optionally run gulp watch to auto bundle your code changes on update.
Configuration
The configuration for React Blog is stored in config.js It has the following options:

port - The port that your server is listening on, the default port is 9080
baseUrl - The baseUrl that is used for all Ajax requests. The hostname used in the baseUrl must be resolvable on the server side. You may need to update your servers host file to accomplish this. The default base url is http://localhost:9080
pageTitle - The text that appears in the top left home link for the blog. The default value is React Blog
itemsPerPage - The amount of list items to display per page. The The default value is 5
maxPageButtons - The maximum amount of paging buttons to display in list view before collapsing. The default value is 3
Developing Blog content
All Blog content is configured in public/static/posts.json. posts.json contains two fields postListContent and posts

postListContent
Contains three fields:

header - This is the header that appears in the post list view. This value is text only.
content - This is the description that appears in the post list view. You may use html in this field.
metaDescription - This is the meta description tag that is used for seo in list view.
posts
Contains seven fields, some are optional:

id - A unique id for the article, this will not be seen by anyone.

slug - The url format for the article post. This cannot contain spaces.

metaDescription (Optional) - This is the meta description tag that is used for seo when the article is shown.

description (Optional) - This is a string containing html content for your post. This should only be used if you are not including a file.

includes (Optional) - This is a JSON array of include objects.

Each include object has the following fields:

type - Valid types are as follows:
css - custom styles to apply to the article. Every article inherits bootstrap 3 css by default.
html - custom html content for your post.
js - custom javascript content for your post
md - a markdown file for your post
jsx - a React component to use for your post. You can write custom React components and import them into your React component using commonJS. You can only import one jsx file in the includes for a post.
path - The absolute path in reference to the public/directory eg. /static/md/react-blog.md

