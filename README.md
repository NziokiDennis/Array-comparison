# Array-comparison

function compareArrays(array1, array2) {
 var i, isA1, isA2;
 isA1 = Array.isArray(array1);
 isA2 = Array.isArray(array2);
 if (isA1 !== isA2) { // is one an array and the other not?
 return false; // yes then can not be the same
 }
 if (! (isA1 && isA2)) { // Are both not arrays
 return array1 === array2; // return strict equality
 }
 if (array1.length !== array2.length) { // if lengths differ then can not be the same
 return false;
 }
 // iterate arrays and compare them
 for (i = 0; i < array1.length; i += 1) {
 if (!compareArrays(array1[i], array2[i])) { // Do items compare recursively
 return false;
 } 
 }
 return true; // must be equal
}
