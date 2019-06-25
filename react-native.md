

## Create alias in react-native

I’ve used this workaround before, but didn’t like all of the loose files floating around in my project. All you need to do is create a package.json file in the root of each folder you’d like to alias, containing this:
```
{
  "name": "myAlias"
}
```
Now you can import x from 'myAlias/components/x' from anywhere in your codebase.


https://www.novis.co/post/custom-aliases-in-react-native-with-babel/
