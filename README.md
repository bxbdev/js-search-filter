# js-search-filter
The goal is making a prove right about the logic of search codes. There was failed with search codes in React. Thus, I took the practice codes for ```indexOf()``` instead of using ```includes()```, make sure it would return the accurated results.

Demo in [Codepen](https://codepen.io/fionataeyang/pen/RwYqjyX)

```javascript
const users = [
  "Diana Turcotte", 
  "Magali Upton", 
  "Rod Strosin", 
  "Margret Kuhn", 
  "Otha Sipes", 
  "Helga Dicki", 
  "Abbigail Von",
  "Raegan Huels", 
  "River Nikolaus", 
  "Dedrick Schuster"
]
let query = ""

const list = document.querySelector("#list")
const search = document.querySelector("#search")

renderList(users)

search.addEventListener('change', (e) => {
  if (e.target.value == '') return list.innerHTML = ''
  
})

search.addEventListener('keyup', (e) => {
  if (e.target.value == '')  {
    renderList(users)
  }
  query = e.target.value.toLowerCase()
  result(query)
})

const result = (query) => {
  list.innerHTML = ''
  users.map( user => {
    if (user.toLowerCase().indexOf(query) !== -1) {
        let div = document.createElement('div')
        div.innerHTML = user
        list.append(div)
    }
  })
}

function renderList(arr) {
  arr.map( i => {
    const div = document.createElement('div')
    div.innerHTML = i
    list.append(div)
  })
}

```

```HTML
<div class="container">
  <input id="search" type="text" placeholder="Search">
  <div id="list"></div>
</div>
```


# Refereence
### indexOf
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/indexOf

### includes
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/includes
