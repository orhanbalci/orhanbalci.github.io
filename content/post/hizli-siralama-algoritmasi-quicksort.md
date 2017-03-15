title: Hizli Siralama Algoritmasi (Quicksort)
link: http://orhanbalci.net/tr/?p=1371
author: Orhan Balci
description: 
post_id: 1371
created: 2015/04/11 04:36:23
created_gmt: 2015/04/11 01:36:23
comment_status: open
post_name: hizli-siralama-algoritmasi-quicksort
status: publish
post_type: post

# Hizli Siralama Algoritmasi (Quicksort)

Javascript implementasyonu : [javascript] /** * Created by Orhan Balci on 10.04.2015. */ var inPlaceQuickSort = function(arrayToBeSorted, beginingIndex, endIndex){ if(beginingIndex < endIndex){ var pivotIndex = partition(arrayToBeSorted, beginingIndex, endIndex); arguments.callee(arrayToBeSorted, beginingIndex, pivotIndex - 1); arguments.callee(arrayToBeSorted, pivotIndex + 1, endIndex); } } var partition = function(arrayToBeSorted, beginingIndex, endIndex){ swap(arrayToBeSorted,Math.round((endIndex+beginingIndex)/2),beginingIndex); var pivotElement = arrayToBeSorted[beginingIndex]; var i,j; var foundLeft = false; var foundRight = false; for(i = beginingIndex + 1, j = endIndex; i < j;){ if(arrayToBeSorted[i] > pivotElement){ foundLeft = true; } if(arrayToBeSorted[j] < pivotElement){ foundRight = true; } if(!foundLeft) i++ if(!foundRight) j--; if(foundLeft && foundRight){ foundLeft = false; foundRight = false; swap(arrayToBeSorted,i,j); i++; j--; } } if(pivotElement > arrayToBeSorted[i]){ swap(arrayToBeSorted,i,beginingIndex); return i; }else{ swap(arrayToBeSorted,i-1,beginingIndex); return i -1; } }; var swap = function(arrayElements, index1, index2){ var tempSwap = arrayElements[index1]; arrayElements[index1] = arrayElements[index2]; arrayElements[index2] = tempSwap; } var printNumbers = function(arrayTobePrinted){ var logMessage = ""; for (var i = 0; i < arrayTobePrinted.length; i++) { logMessage += arrayTobePrinted[i] + " "; } console.log(logMessage); } var testSorting = function() { var numberArray = []; numberArray.length = 100; for (var i = 0; i < numberArray.length; i++) { numberArray[i] = Math.round(Math.random() * 100); } printNumbers(numberArray); inPlaceQuickSort(numberArray,0,99); printNumbers(numberArray); } testSorting(); [/javascript]