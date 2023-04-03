Bankist App
=======================================

HTML, CSS, JavaScript

Main goal -> create a bank app that allows transferring money between different accounts. working with arrays. 

* * *
### [Demo](https://cold-world.github.io/bankist-app/)

use it to login and money transfer:

login 'js'
pin 1111

login 'jd'
pin 2222

login 'stw'
pin 3333

![Alt Text](https://i.ibb.co/M6PYnzh/Screenshot-2023-04-03-120740.jpg)

* * *



### A piece of code

```btnTransfer.addEventListener('click', (e) => transfer(e));

function transfer(e) {
  e.preventDefault();
  const amount = Number(inputTransferAmount.value);
  const receiverAcc = accounts.find((item) => item.userName === inputTransferTo.value);
  inputTransferAmount.value = inputTransferTo.value = '';
  
  if (
    amount > 0 &&
    receiverAcc &&
    currentUser.balance >= amount &&
    receiverAcc.userName !== currentUser.userName
  ) {
    currentUser.movements.push(-amount);
    currentUser.movementsDates.push(new Date().toISOString());
    receiverAcc.movements.push(amount);
    receiverAcc.movementsDates.push(new Date().toISOString());
    updateUI(currentUser);
    clearInterval(timer);
    timer = startLogOutTimer();
  }
}
```

### Download & Installation

```shell 
git clone https://github.com/cold-world/bankist-app.git
cd <project dir>
yarn install
yarn start
```
