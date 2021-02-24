```javascript
/**
 * @param {number[]} nums
 * @param {number} target
 * @return {number[]}
 */
const twoSum = function(nums, target) {
    
    const exaNum = [];
    
    nums.forEach((item,index,arr) => {
        
        const isNum = target - item;

        if(arr.includes(isNum,index+1)){
             exaNum.push(index);
             exaNum.push(arr.indexOf(isNum,index+1));
        }
    });
    
    return exaNum;
};

```
