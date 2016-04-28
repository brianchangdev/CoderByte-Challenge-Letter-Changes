# CoderByte-Challenge-Letter-Changes

// Using the JavaScript language, have the function LetterChanges(str) take the str parameter being passed and modify it using the 
// following algorithm. Replace every letter in the string with the letter following it in the alphabet (ie. c becomes d, z becomes a).  // Then capitalize every vowel in this new string (a, e, i, o, u) and finally return this modified string. 

function LetterChanges(str) { 
// first establish which letters you will be replacing using a RegEx
  var alphabet = /[a-zA-Z]/g;
// a function below to change letters for the next one in alphabet (see line 17)
// create a new string that will take str and replace alphabet with next letter after
    var newStr = str.replace(alphabet, replaceLetter);
  
// now do same with vowels  
  var vowel = /[aeiou]/g;
// now to uppercase all vowels
  newStr.replace(vowel, replaceVowel);
 
  return newStr; 
}

 // functions below relate to above
function replaceLetter(match){
 // because next letter of z needs to loop back to a
 if(match === 'z'){
  return 'a'
 }
  // create variable that will default the char to its ascii number
  var ascii = match.charCodeAt(0);
  // and return calling String method add 1 to the ascii number to move to next leter in alphabet
  return String.fromCharCode(ascii + 1);
  }
// function to replace vowels relating to above
function replaceVowel(match){
  // if vowel then change to uppercase
 return match.toUpperCase(); 
}
  
