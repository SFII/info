# What's going on with all.js? 

If you see ```src/static/javascripts``` you will notice a bunch of JS files with the different classes split up logically. We use gulp to take all of these files, and combine them into a single file all.js. The advantage to this is that it runs faster than multiple files and we can apply minification/translation to this big file when we run in prod. For now, though all JS work should go into ```javascripts/```. 

*MAKE SURE YOU HAVE CACHING OFF* 
all.js is changed after every compilation. Some browsers cache the data associated with a webpage and this means our changes won't show up when we change the file. 
- [Chrome](http://stackoverflow.com/questions/5690269/disabling-chrome-cache-for-website-development)
- [Firefox](https://support.mozilla.org/en-US/questions/905902)

# Working with gulp 

Gulp can perform all of these tasks for you automatically. You can install everything for gulp when you run ```npm install``` from the root directory. This is done for you when you run ```make build```. If you make a change to one of the js files and you want to compile the changes, run ```gulp dev-js``` this will perform the compilation and translation as well as linting to make sure your JS doesn't contain any errors. 

If you notice in gulpfile.js, I list all of the files we need to compile in [sequential order](https://github.com/SFII/scq/blob/master/gulpfile.js#L16-L21). This is because during concatination into one big file, we need to make sure that the order of decleration makes sense. We can't refer to a variable that hasn't been decalred yet. So, I manually specify the order gulp should concatenate the files. 

# Workflow for frontend
  1. Change file. 
  2. Run ```gulp dev-js```
  3. Reload webpage. 
