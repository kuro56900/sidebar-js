# Sidebar
Create sidebar/sidenav experiance in pure javascript.

```ssh
npm install sidebarjs --save
```

## Options
| Option | Default | Type | Description |
| :----- | :------ | :--- | :---------- |
| `documentMinSwipeX` | 10 | Number | Minimum swipe in px required to trigger listener: open |
| `documentSwipeRange` | 40 | Number | Range in px where document is listening for gesture: open |
| `nativeSwipe` | true | Boolean | Open and close sidebar with swipe gestures |
| `nativeSwipeOpen` | true | Boolean | Enable/Disable open on swipe
| `position` | 'left' | String | Sidebar position, accepted values: left\right |

``` JS
var rightSidebarjs = new SidebarJS('navbar', {
  documentMinSwipeX: 10,
  documentSwipeRange: 40,
  nativeSwipe: true,
  nativeSwipeOpen: true,
  position: 'left',
});
```

## Implementation - Superfast explanation
**sidebarjs.css**と**sidebar.js**を読み込んでください。(minファイルにしたほうがいい)  
サイドバーのDIVタグにIDを設定して、トグルボタンは設定したID+"-toggle"にしてください。  
[id="DOM"],[id="DOM-toggle"]  
All contents you will write inside tag[sidebarjs] will be rendered inside the sidebar.  
Then simply init it with **new SidebarJS("#DOM")** and you are ready!

## Implementation - Explanation step by step
### Download files
Download and save all files
```ssh
$ npm install sidebar-js --save
```

Insert _sidebarjs.css_ and _sidebarjs.js_ in your index.html.


### Create SidebarJS element
Write **[sidebarjs]** attribute inside a tag (div, aside, or whatever you want).
```html
<div sidebarjs>
  <div>Title</div>
  <nav>
    <a href="link">Home</a>
    <a href="link">About</a>
    <a href="link">Contacts</a>
  </nav>
</div>
```

### Trigger button
Do you need a trigger button for open/close SidebarJS? Just put **[sidebarjs-toggle]** attribute inside a tag and it's done!
```html
<div sidebarjs-toggle>Open/Close</div>
```

### Init
When you have files, [sidebarjs] and [sidebarjs-toggle] you can init your SidebarJS Module like:
```js
var sidebarjs = new SidebarJS("sidebarjs")
```

### Full file example
```html
<head>

  <link rel="stylesheet" href="your/path/sidebarjs.css">

</head>
<body>

  <div id="navbar-toggle">Open/Close</div>

  <div id="navbar">
    <div>Title</div>
    <nav>
      <a href="link">Home</a>
      <a href="link">About</a>
      <a href="link">Contacts</a>
    </nav>
  </div>

  <script src="your/path/sidebarjs.js"></script>
  <script>
    // Init SidebarJS
    var sidebarjs = new SidebarJS("#navbar");
  </script>

</body>
```