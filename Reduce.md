## Flatten a deeply nested arrays

```
const data = [1, [2, [3, [4]], 5]];

function flatten(data) { 
    return data.reduce((acc, element)=>{
        if (Array.isArray(element)){
            return [...acc, ...flatten(element)]
        }
        else return [...acc, element]
    },[])
}

console.log(flatten(data))
```

## Group by key

```
const groupByKey =  users.reduce((acc, user)=>{
    return {
        ...acc, 
        [user.role]:[ user, ...(acc?.[user.role] || [])]
        }
    },{})

console.log(groupByKey)
```

## Count frequency of items
```
const words = ["apple", "banana", "apple", "orange", "banana", "apple"];


const counts = words.reduce((counter_obj, word)=>{
    if (counter_obj && Object.keys(counter_obj).includes(word)){
        return {
            ...counter_obj,
            [word]: counter_obj[word]+1
        }
    }
    else return {
        ...counter_obj,
        [word]: 1
    }
},{})

console.log(counts)
```
