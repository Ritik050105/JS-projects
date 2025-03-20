loops:
entry control-for ,while
exit control-do while
functions :
user defined and pre defined
predefined:array object math string date&time
userdefined:no argument no return,no argument with return,with argument no return,with argument with return
project:to do list using array function
array predefined function -> push -> to add an element in the end of an array,forEach()->to access the array's each elements
program:(to do list using array function)
index.html:
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <form>
        <div>
            <label>Username</label>
            <input type="text" id="uname" value="" placeholder="Enter a username"/>
        </div>
        <div>
            <label>Password</label>
            <input type="curent-password" id="pass" value="" placeholder="Enter a password"/>
        </div>    
        <div>
            <input type="button" value="Click" id="btn1"/>
        </div>
    </form>
    <form>
        <div>
            <input type="text" id ="todo" value="" placeholder="enter a todo"/>
        </div>
        <div>
            <input type="button" value="Click" id="btn2"/>
        </div>
    </form>
    <table>
        <thead>
            <tr>
                <th>s:no</th>
                <th>Description</th>
                <th>Action</th>
            </tr>
        </thead>
        <tbody id="tbl">
        </tbody>
    </table>
    <script src="/javascript/app.js"></script>
</body>
</html>
app.js:
let itemList = [];
let addItem = () =>{
    let item = document.getElementById('todo').value;
    itemList.push(item);
    console.log(itemList);
    document.getElementById('todo').value="";
    getItem();
};
let getItem =() =>{
    let emptystr = "";
    let sno=0;
    itemList.forEach(function(value,index){
        sno +=1;
        emptystr +="<tr><td>"+sno+"</td><td>"+value+"</td><td>Remove</td></tr>";
    })
document.getElementById('tbl').innerHTML=emptystr;
}
document.getElementById('btn2').addEventListener('click',addItem);