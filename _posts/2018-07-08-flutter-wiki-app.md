---
layout: post
title: "Flutter Wiki App"
description: "A simple app to keep track of Flutter packages and access the docs easily. It was intended to be like a little guideline and wikipedia for the Flutter SDK and those who work with it. It has three main features including the docs, the package list and a tag that adds your favorite packages to a list."
thumb_image: "documentation/sample-image.jpg"
tags: [flutter]
---

<div id="github-content"></div>
<script>$("#github-content").load("https://raw.githubusercontent.com/bostrot/flutter_repo_wiki/master/README.md", function() {
  document.getElementById('github-content').innerHTML = marked(document.getElementById('github-content').innerHTML);
});
</script>