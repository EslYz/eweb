# 稀疏数组
```javascript
   // 初始化棋盘，0 表示没有棋子， 1:黑子，2：白子
let chessArr = []
for (let i = 0; i < 11; i++) {
    chessArr[i] = []
    for (let j = 0; j < 11; j++) {
        chessArr[i][j] = 0
    }
}
chessArr[1][2] = 1
chessArr[2][3] = 2

// 将二维数组转换为稀疏数组
function transform(arr, len) {
    let sum = 0
    // 遍历数组，找出有多少不是0 的
    for (let i = 0; i < 11; i++) {
        for (let j = 0; j < 11; j++) {
            if (arr[i][j] !== 0) {
                sum++
            }
        }
    }
    // 创建对应的稀疏数组
    let sparseArr = []
    sparseArr[0] = [len, len, sum]
    //遍历二维数组，将非0的值存到稀疏数组中
    let count = 0;// 用于记录是第几个非0 数据
    for (let i = 0; i < len; i++) {
        for (let j = 0; j < len; j++) {
            if (arr[i][j] !== 0) {
                count++
                sparseArr[count] = [i,j, arr[i][j]]
            }
        }
    }
    return sparseArr
}

// 将稀疏数组还原为源数组
function parse(sparseArr, row, col) {
    let ans = []
    for(let i = 0; i < row; i++) {
        ans[i] = []
        for (let j = 0; j < col; j++) {
            ans[i][j]=0
        }
    }
    for (let i = 1; i < sparseArr.length; i++) {
        let temp = sparseArr[i]
        ans[temp[0]][temp[1]] = temp[2]
    }
    return ans
}

let r = transform(chessArr, 11)
console.log(parse(r, 11, 11))
    

```