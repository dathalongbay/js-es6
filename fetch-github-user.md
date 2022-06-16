

# HTML
```
<div>
  <input type="text" name="user" id="user" value="" />
  <button id="fetch-user">Fetch github user info</button>
</div>

<div id="result"></div>
<div id="resultDetail"></div>
```
# JS 
```
document.getElementById("fetch-user").onclick = function() {
  var user = document.getElementById("user").value;
  if (user) {
    fetch('https://api.github.com/users/'+user)
    .then(response => response.json())
    .then(info => {
      console.log(info);
      document.getElementById("result").innerHTML = JSON.stringify(info);
      var htmlAppend = '';
      for(let x in info) {
        console.log(x + ' : ' + info[x]);
        htmlAppend += '<p>'+x + ' : ' + info[x]+'</p>';
      }
      document.getElementById("resultDetail").innerHTML = htmlAppend;
      
    });
  }
} 
```

![image](https://user-images.githubusercontent.com/6966136/173989670-28f5608e-e634-45a0-9768-b10afd938545.png)

