# 顺序存储二叉树

```javascript
    let arr = [1,2,3,4,5,6,7]
    class ArrBinaryTree {
        constructor(arr) {
            this.arr = arr
        }
        // index 是数组下标
        preOrder(index) {
            if (this.arr === null || this.arr.length === 0) {
                return
            }
            console.log(this.arr[index])
            if ((index * 2 + 1) < this.arr.length) {
                this.preOrder(index * 2 + 1)
            }
            if ((index * 2 + 2) < this.arr.length ) {
                this.preOrder(index * 2 + 2)
            }
        }
        infixOrder(index) {
            if (this.arr === null || this.arr.length === 0) {
                return
            }
            if ((index * 2 + 1) < this.arr.length) {
                this.infixOrder(index * 2 + 1)
            }
            console.log(this.arr[index])
            if ((index * 2 + 2) < this.arr.length ) {
                this.infixOrder(index * 2 + 2)
            }
        }
        postOrder(index) {
            if (this.arr === null || this.arr.length === 0) {
                return
            }
            if ((index * 2 + 1) < this.arr.length) {
                this.postOrder(index * 2 + 1)
            }
            if ((index * 2 + 2) < this.arr.length ) {
                this.postOrder(index * 2 + 2)
            }
            console.log(this.arr[index])
        }
    }
    let tree = new ArrBinaryTree(arr)
    tree.infixOrder(0)

```