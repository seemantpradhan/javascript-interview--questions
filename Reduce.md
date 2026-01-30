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
