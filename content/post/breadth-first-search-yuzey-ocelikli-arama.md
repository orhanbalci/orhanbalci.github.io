title: Breadth First Search (Yuzey Ocelikli Arama)
link: http://orhanbalci.net/tr/?p=1380
author: Orhan Balci
description: 
post_id: 1380
created: 2015/04/19 05:43:26
created_gmt: 2015/04/19 02:43:26
comment_status: open
post_name: breadth-first-search-yuzey-ocelikli-arama
status: publish
post_type: post

# Breadth First Search (Yuzey Ocelikli Arama)

Javascript implementasyonu : [javascript] var adjecencyList = []; var nodes = []; fs = require('fs') fs.readFile('C:/Users/admin/WebstormProjects/untitled/breadth_first_search.txt', 'utf8', function (err, graph_data) { if (err) { return console.log(err); } var edges = graph_data.split("\r\n"); breadth_first_search(edges); }); function buildAdjecencyList(edges) { edges.every(function (edge, index) { if (index === 0) { //node count edge count adjecencyList = new Array(edge.split(" ").map(function (item) { return parseInt(item); })[0]) return true; } vertices = edge.split(" ").map(function (item) { return parseInt(item); }); if (nodes[vertices[0]] === undefined) nodes[vertices[0]] = {vertex: vertices[0], shortestDistance: Number.MAX_VALUE}; if (nodes[vertices[1]] === undefined) nodes[vertices[1]] = {vertex: vertices[1], shortestDistance: Number.MAX_VALUE}; if (adjecencyList[vertices[0]] === undefined) adjecencyList[vertices[0]] = []; adjecencyList[vertices[0]].push(nodes[vertices[1]]); return true; }) } var breadth_first_search = function (edges) { var result = ""; buildAdjecencyList(edges); var processQueue = []; nodes[1].shortestDistance = 0; processQueue.push(nodes[1]); while (processQueue.length > 0) { var node = processQueue.shift(); if (node.shortestDistance < Number.MAX_VALUE) { if (adjecencyList[node.vertex] === undefined) { continue; } for (var i = 0; i < adjecencyList[node.vertex].length; i++) { adjecentNode = adjecencyList[node.vertex][i]; if (adjecentNode.shortestDistance === Number.MAX_VALUE) { processQueue.push(adjecentNode); adjecentNode.shortestDistance = node.shortestDistance + 1; } } } } nodes.every(function (node) { if (node.shortestDistance === Number.MAX_VALUE) { result = result.concat(-1).concat(" "); } else { result = result.concat(node.shortestDistance).concat(" "); } return true; }) console.log(result); } [/javascript] [ad#Yazi Ici Buyuk]