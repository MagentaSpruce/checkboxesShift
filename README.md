# checkboxesShift
Part of 30 day JS Challenge

This demonstrates how to create a form which has multiple checkboxes which can be checked simultaneously upon holding down the shift key.

This project helped me to better learn and understand the following:
1) dd
2) 2d
3) fdd
4) ffd
5) fff


A simple explanation of the code is below:


Select all the checkboxes so that event listeners can be used to determine when they are checked.
```JavaScript
 const checkboxes = document.querySelectorAll('.inbox input[type="checkbox"]');
```

Listen for when a checkbox gets clicked/changed.
```JavaScript
checkboxes.forEach(checkbox => checkbox.addEventListener('click', handleCheck));
```

Create the handleCheck function. First checked box needs to be put into a variable (lastChecked) so that when the second checkbox is checked while holding shift, the code knows where to start from. inBetween is set to false and if the shift key is down and and a last input made then for each input in between the checkBox.checked is set to true, crossing out the elements.
```JavaScript
  let lastChecked;
  function handleCheck(e){
 
    let inBetween = false;
    if(e.shiftKey && this.checked){
      checkboxes.forEach(checkbox => {
        if(checkbox === this || checkbox === lastChecked){
          inBetween = !inBetween;
        }
        if(inBetween){
          checkbox.checked = true;
        }
      })

    }
    lastChecked = this;
  }
```

***End Walkthrough
