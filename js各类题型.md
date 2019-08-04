# javascript  


 ##  已知如下数组，编写一个程序将数组扁平化去并除其中重复部分数据，最终得到一个升序且不重复的数组

     var arr = [ [1, 2, 2], [3, 4, 5, 5], [6, 7, 8, 9, [11, 12, [12, 13, [14] ] ] ], 10];
    
     Array.from(new Set(arr.flat(Infinity))).sort((a,b)=>{ return a-b})===> (14) [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14]


 ## js获取鼠标选中的值

    const SelectText = () => {
        try {
            var selecter = window.getSelection().toString()
            if (selecter !== null && selecter.trim() !== "") {
                selText = selecter
            } else {
                selText = ""
            }
        } catch (err) {
            var st = document.selection.createRange()
            var s = st.text
            if (s !== null && s.trim() !== "") {
                selText = s
            } else {
                selText = ""
            }
        }
    }