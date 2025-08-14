# JavaScript-Project
My first JS project: Grade Calculator
<br>
Author: Tamasa Paul
<br>
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
