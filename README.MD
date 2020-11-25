# 1 Create Folders
1. create and open in vscode folder >jshop and create structure > frontend/src/index.html 
2. use html:5 in index and change title
3. convert to npm project frontend>npm init  -frontend is now node project  (to show using live server package)
4. install live-server >npm install -D live-server
5. create start script - "live-server src --verbose"
6. run npm start
   #### notes: the benefit of live server is that we can see the changes automatically in the browser

# 2 Design Website
1. create style css in src folder
2. link it in index.html
3. create div grid container with header main and footer
4. add divs in header one for brand and one for signin and cart 
5. add some text in main and footer- just for now
6. styling html font-size: 62.5% --> 16px * 62.5 = 10px = 1rem  
7. style grid-container, header, main and footer (#203030, #f03040)

# 3 Create Static Homescreen
1. create ul.products
2. create li
3. create div.product
4. add img, .product-name, .product-brand, .product-price
5. style ul products and internal divs
6. duplicate li several times to show several products

# 4 Render Dynamic Homescreen
1. create data.js
2. export an array of 6 products
3. create screen/HomeScreen.js
4. export HomeScreen as an object with render() method
5. implement render()
6. import data.js
7. return products mapped to lis inside the ul
8. create app.js
9. link it to index.html as a module
10. set main id to main_container
11. create router() function
12. set main_container innerHTML to HomeScreen.render()
13. need to import HomeScreen, so make sure you do the export
14. set load event of window to router() function 
15. .join('\n') after map() to eliminate ' , ' after product
16. remove the static content, now data is dynamic

# 5 Build Url Router
1. create routes as route:screen object for home screen
2. create utils.js
3. export parseRequestURL()
4. set url as hash address split by slash
5. return resource , id and verb of url
6. update router()
7. set request as parseRequestURL()
8. build parseUrl and compare with routes
9. if route exists render it, else render Error404
10. create screens/Error404.js and render error message


# 6 Create Node.JS Server

1. run npm init in root folder
2. npm install express
3. create server.js
4. add start command as node backend/server.js
5. require express
6. move data.js from frontend to backend
7. create route for api/products
8. return products in data.js
9. npm start

# 7 Load Products From Backend
1. edit HomeScreen.js
2. make render async
3. fetch products from '/api/products' in render()
4. make router() async and call await HomeScreen.render()
5. use cors on backend