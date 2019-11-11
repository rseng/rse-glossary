---
layout: page
title: Term Definition
permalink: /term/
form: true
---

<!-- Page Content -->
<div class="container">
  <div class="row">
      <h5>What does it mean for research software engineering?</h5>
      <div id="term-definition">
      </div>
      <a id="term-link" href="#" target="_blank" hidden><button class="btn btn-info" style="margin-top:20px">More</button></a>
  </div>
</div>
<script>

// populate page with all terms and definitions
terms = { {% for term in site.data.terms %}"{{ term.name }}": {"definition": "{{ term.definition }}", "url": "{{ term.url }}"} {% if forloop.last %}{% else %},{% endif %}{% endfor %}}
console.log(terms)
function getUrlVars() {
    var vars = {};
    var parts = window.location.href.replace(/[?&]+([^=&]+)=([^&]*)/gi, function(m,key,value) {
        vars[key] = value;
    });
    return vars;
}

var term = getUrlVars()["q"];
term = decodeURI(term);

if (term in terms) {
  console.log(term)
  document.getElementById('page-title').innerHTML = term;
  document.getElementById('term-definition').innerHTML = terms[term]["definition"];
  if ("url" in terms[term]) {
    var url = terms[term]["url"]
    if (url != "") {
      document.getElementById('term-link').href = terms[term]["url"]
      document.getElementById('term-link').hidden = false
    }
  }
} else {
  document.getElementById('term-definition').innerHTML = "We couldn't find the term " + term + " in our lookup. Perhaps you can contribute it?";
}
</script>
