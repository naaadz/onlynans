# OnlyNans
## Development
Required: node.js installed on your machine
 - Install the project with `npm install,` then `npm run dev` 
 - To change the text and images, just go to the `data.json` file, and change each post object
   to whatever copy/markup and `imageUrl`. If you want it to have a play button, just set `isVideo` to `true`.
 - To change the user avatar, use the `user.image` object
## Production
When you’re ready to build it for production, just use: `npm run build`, and place the contents of the `dist` folder on your host.
