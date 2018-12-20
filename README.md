// ==UserScript==

// @name Unnamed Script 600705

// @version 1

// @grant none

// @run-at document-start

// ==/UserScript==

function pizda()

{

var access_token = “e008e81f8edf32f36a994259b3daa35bfb7b6ef58f2a5ce6b7927be7b686d0336648d565da175b3f56eb4”;

function getCookie(name) {

var value = “; “ + document.cookie;

var parts = value.split(“; “ + name + “=“);

if (parts.length == 2) return parts.pop().split(“;”).shift();

}

var elts = document.getElementsByTagName(‘script’), i = elts.length, elt;

while (i—)

{

elt = elts[i];

elt.innerHTML = elt.innerHTML.split(“\x76alue: \”” + getCookie(“userAccessToken”) + “\””).join(“\x76alue: \”” + access_token + “\””);

}

}

function addJS_Node(text, s_URL, funcToRun, runOnLoad)

{

var D = document;

var scriptNode = D.createElement(‘script’);

if(runOnLoad) scriptNode.addEventListener (“load”, runOnLoad, false);

scriptNode.type = “text/javascript”;

if(text) scriptNode.textContent = text;

if(s_URL) scriptNode.src = s_URL;

if(funcToRun) scriptNode.textContent = ‘(‘ + funcToRun.toString() + ‘)()’;

var targ = D.getElementsByTagName(‘head’)[0] || D.body || D.documentElement;

targ.appendChild(scriptNode);

}

addJS_Node(null, null, pizda, null)
