# JavaScript-Project
My first JS project: Grade Calculator
<br>
Author: Tamasa Paul
<br>
JS Code
```
console.log("This is a grade converter app");
const resetBtn = document.querySelector("#Reset");
const calcBtn = document.querySelector("#Calculator");
const gradeInput = document.querySelector(".input input");
const percentage = document.querySelector(".input input#Percentage");
const scale10 = document.querySelector("#btn10");
const scale5 = document.querySelector("#btn5");

resetBtn.addEventListener("click", ResetFunction);
 function ResetFunction(){
    gradeInput.value="";
    percentage.value="";
     scale10.style.backgroundColor="";
      scale5.style.backgroundColor="";
 }


let selectedScale= 10;
scale10.addEventListener("click",()=>{
    selectedScale= 10;
    scale10.style.backgroundColor= "skyblue";
     scale10.style.color= "black";
    console.log("Scale 10 selected");
    scale5.style.backgroundColor= "";
})

scale5.addEventListener("click",()=>{
    selectedScale= 5;
    scale5.style.backgroundColor= "skyblue";
    scale5.style.color= "black";
    console.log("Scale 5 selected");
    scale10.style.backgroundColor= "";

})
calcBtn.addEventListener("click", gradeConverterFunction);
 function gradeConverterFunction(){
    const grade= Number(gradeInput.value);
    if(gradeInput.value===""|| isNaN(grade)){
        alert (`Please enter a valid grade between 0 and 10`);
        return ;

    } 
    
    if(selectedScale===10){
        if(grade<0 || grade>10){ 
            alert (`Please enter a valid grade between 0 and 10`);
            return;
        }
 percentage.value= (grade * 9.5).toFixed()+`%`;

    } else if(selectedScale===5){
        if(grade<0 || grade>5){
            alert (`Please enter a valid grade between 0 and 5`);
            return;
        }
        percentage.value= ((grade / 5) *100).toFixed()+`%`;
    }
    console.log("Grade converted successfully");
};
```
<br>
CSS Code
```
*{
    margin: 0;
    padding: none;
}
.box-container{
    display:flex;
    justify-content: center;
    align-items: center;
    justify-items: center;
    width: 100vw;
    height:100vh;
    background-color: #aec1d4;
   
    background-color: #9ed4ef;
}

h1{
    text-align: center;
    font-size:2rem;  
}
input{
        justify-content: center; 
        align-items: center;
        width: 100%;
        text-align: center;

    }
.container{
    height:50vh;
    width: 40vh;
    background-color: beige;
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    align-items: center;
    justify-items: center;
    font-size: 1.5rem;
    border-radius: 1rem;
     padding:2rem;
    margin:1rem 1.5rem 0rem 1.5rem;
}
.button-holder{
    display: flex;
    justify-content: center;
    align-items: center;
    justify-items: center;
    gap:1rem;
   
}
#btn10{
    width:12rem;
    height:2.5 rem;
    font-size: 1rem;
    border-radius: 1rem;
    background-color:#782835;
    border: none;
    padding:1rem;
    color: #efdec3;
    cursor:pointer;
}
#btn5{
    width:12rem;
    height:2.5 rem;
    font-size: 1rem;
    border-radius: 1rem;
    background-color:#782835;
    border: none;
    padding:1rem;
    color: #efdec3;
     
    cursor:pointer;
}
.input{
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    justify-items: center;
    gap:1rem;
    width: 100%;
}
input{
    width:100%;
    height: 1.2rem;
    font-size: 1.2rem;
    border-radius: 1rem;
    border:1px solid #888f92;
    padding:1rem;
}
.btn{
    display: flex;
    justify-content: center;
    align-items: center;
    justify-items: center;
    gap:2rem;
}

#Calculator, #Reset{
    background-color: rgb(244, 191, 125);
    border: none;
    width:11rem;
    height:2.5rem;
    border-radius: 1rem;
    font-size: 1rem;
    font-weight: 550;
    padding:1.5rem;
    display: flex;
    align-items: center;
    justify-content: center;
    text-align: center;
    cursor: pointer;

}
#Reset{
    background-color: #d99031;
   
}

```
