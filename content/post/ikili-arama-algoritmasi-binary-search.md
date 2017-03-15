title: Ikili Arama Algoritmasi (Binary Search)
link: http://orhanbalci.net/tr/?p=1376
author: Orhan Balci
description: 
post_id: 1376
created: 2015/04/13 23:33:15
created_gmt: 2015/04/13 20:33:15
comment_status: open
post_name: ikili-arama-algoritmasi-binary-search
status: publish
post_type: post

# Ikili Arama Algoritmasi (Binary Search)

Javascript implementasyonu : [javascript] var binarySearch = function(searchArray, beginIndex, endIndex, targetValue) { if (beginIndex > endIndex) { return -1; } if (searchArray[Math.floor((beginIndex + endIndex) / 2)] === targetValue) return Math.floor((beginIndex + endIndex) / 2) + 1; else if (searchArray[Math.floor((beginIndex + endIndex) / 2)] > targetValue) return arguments.callee(searchArray, beginIndex, Math.floor((beginIndex + endIndex) / 2)-1, targetValue); else if (searchArray[Math.floor((beginIndex + endIndex) / 2)] < targetValue) return arguments.callee(searchArray, Math.floor((beginIndex + endIndex) / 2)+1, endIndex, targetValue); else console.log("Error"); } [/javascript] [ad#Yazi Ici Buyuk]