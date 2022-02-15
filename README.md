let myImage = document.querySelector('img');
myImage.onclick = function() {
    let mySrc = myImage.getAttribute('src');
    if(mySrc === 'images/piotrkow-trybunalski.jpg') {
        myImage.setAttribute('src','images/piotrkow-trybunalski2.jpg');
    } else {
        myImage.setAttribute('src','images/piotrkow-trybunalski.jpg');
    }
}
let myButton = document.querySelector('button');
let myHeading = document.querySelector('h1');
function setUserName() {
    let myName = prompt('Please enter your name.');
    if(!myName) {
        setUserName(); } else {
    localStorage.setItem('name', myName);
    myHeading.textContent = 'Nasze miasto - Piotrków Trybunalski, ' + myName;
        }
}
if(!localStorage.getItem('name')) {
    setUserName();
} else {
    let storedName = localStorage.getItem('name')
    myHeading.textContent = 'Nasze miasto - Piotrków Trybunalski, ' + storedName;
}
myButton.onclick = function() {
    setUserName();
  }
