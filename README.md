# JavaScript Interview Series
This repo created for interview based questions & concepts for JavaScript😊

Question 1.
Polyfills of map method of Array

Array.prototype.myMap = function (callback) {
    let res = []
   
    for (let i = 0; i <= this.length - 1; i++) {
        res.push(callback(this[i], i, this))
    }

    return res
}

let nums = [2, 3, 4, 5]
const newArry = nums.myMap((elem, i, arr) => {
    return elem * 4
})

console.log(newArry)


Question 2.
Polyfills of filter method of Array.

Array.prototype.myFilter = function (cb) {
    let res = []

    for (let i = 0; i <= this.length - 1; i++) {
        let results = cb(this[i], i, this)
        if (results) {
            res.push(this[i])
        }
    }

    return res
}


let nums = [2, 3, 4, 5]
const newArray = nums.myFilter((elem, i, nums) => {
    return elem >= 5
})

console.log(newArray)

Question 3
Polyfills of reduce method of Array.

Array.prototype.myReduce = function (cb, intialVal) {
    let acc = intialVal === undefined ? this[0] : intialVal;
    let i;
    if (intialVal === undefined) {
        i = 1;
    }
    else {
        i = 0;
    }
    for (let j = i; j <= this.length - 1; j++) {
        acc = cb(acc, this[j], j, this)
    }
    return acc
}


let nums = [2, 3, 4, 5]
const sum = nums.myReduce((a, elem,) => {
    return a + elem
}, 10)

console.log(sum)


