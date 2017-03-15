title: Depth First Search (Derinlik Oncelikli Arama)
link: http://orhanbalci.net/tr/?p=1384
author: Orhan Balci
description: 
post_id: 1384
created: 2015/04/19 19:44:47
created_gmt: 2015/04/19 16:44:47
comment_status: open
post_name: depth-first-search-derinlik-oncelikli-arama
status: publish
post_type: post

# Depth First Search (Derinlik Oncelikli Arama)

Derinlik oncelikli aram algoritmasi kullanarak graf uzerinde bagli bilesen sayisi bulma. Javascript implementasyonu : [javascript] var adjecencyList = []; var nodes = []; fs = require('fs') fs.readFile('./depth_first_search.txt', 'utf8', function (err, graph_data) { if (err) { return console.log(err); } var edges = graph_data.split("\r\n"); label_connected_components(edges); }); function find_starting_node() { for (var i = 1; i < nodes.length; i++) { if(nodes[i] != undefined && nodes[i].connected_group === Number.MAX_VALUE) return nodes[i]; } return undefined; } function label_connected_components(edges){ build_adjecency_list(edges); var label_counter = 1; var starting_node = undefined; while((starting_node = find_starting_node()) != undefined) { depth_first_search(label_counter, starting_node); label_counter++; } console.log(label_counter-1); } function build_adjecency_list(edges) { edges.every(function (edge, index) { if (index === 0) { //node count edge count adjecencyList = new Array(edge.split(" ").map(function (item) { return parseInt(item); })[0]); nodes = new Array(edge.split(" ").map(function (item) { return parseInt(item)+1; })[0]); for (var i = 0; i < nodes.length; i++) { nodes[i] = {vertex: i, connected_group: Number.MAX_VALUE}; } return true; } var vertices = edge.split(" ").map(function (item) { return parseInt(item); }); if (adjecencyList[vertices[0]] === undefined) adjecencyList[vertices[0]] = []; if (adjecencyList[vertices[1]] === undefined) adjecencyList[vertices[1]] = []; adjecencyList[vertices[0]].push(nodes[vertices[1]]); adjecencyList[vertices[1]].push(nodes[vertices[0]]); return true; }) } var depth_first_search = function (connected_group_label, starting_node) { var processQueue = []; processQueue.push(starting_node); while (processQueue.length > 0) { //depth first search icin processQueue stack biciminde calismali var node = processQueue.shift(); if (node.connected_group === Number.MAX_VALUE) { node.connected_group = connected_group_label; if (adjecencyList[node.vertex] === undefined) { continue; } for (var i = 0; i < adjecencyList[node.vertex].length; i++) { var adjecentNode = adjecencyList[node.vertex][i]; if (adjecentNode.connected_group === Number.MAX_VALUE) { processQueue.unshift(adjecentNode); //unshift arrayin basina ekleme yapar } } } } } [/javascript] [ad#Yazi Ici Buyuk]