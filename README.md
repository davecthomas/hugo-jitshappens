# JitsHappens
JitsHappens is a blog site that uses Hugo static site generation code for the static content. It requires a the golang Heroku http app that references this static content.

## 1. Get the code local
This requires 2 separate git projects. One is the static site generator. The other is a simple go app that serves the static files.
```
mkdir hugo-jitshappens
cd hugo-jitshappens
git init .
git remote add github git@github.com:davecthomas/hugo-jitshappens.git
git pull github master
cd ..
mkdir go-jitshappens
cd go-jitshappens
git init .
git remotre add github git@github.com:davecthomas/go-jitshappens.git
git pull github master
```

## 2. Install dependencies
You may need to downgrade Hugo to get this to work correctly
```
brew install hugo
brew switch hugo 0.17
```

## 3. Generate the static files
This will save files to ../go-jitshappens/public
```
hugo
```

## 4. Hosting the site
On Heroku, for example. Push just the static files to your github pipeline to your web server.
```
cd ../go-jitshappens
git add .
git commit -m “New stuff”
git push <your repo> master
```
