## Welcome to GitHub Pages

You can use the [editor on GitHub](https://github.com/Santiagovicentedelatorre/santiagovicentedelatorre.github.io/edit/master/index.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/Santiagovicentedelatorre/santiagovicentedelatorre.github.io/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.

<script src="https://www.gstatic.com/dialogflow-console/fast/messenger/bootstrap.js?v=1"></script>
<df-messenger
  intent="WELCOME"
  chat-title="Nividia"
  agent-id="3b919bf0-8261-45ac-9486-d7a642ceece7"
  language-code="en"
></df-messenger>

<script src="https://www.gstatic.com/dialogflow-console/fast/messenger/bootstrap.js?v=1"></script>
<df-messenger intent="WELCOME" chat-title="Nividia" agent-id="3b919bf0-8261-45ac-9486-d7a642ceece7" language-code="en"

Teachable Machine Image Model - p5.js and ml5.js
<script src="https://cdnjs.cloudflare.com/ajax/libs/p5.js/0.9.0/p5.min.js"></script> <script src="https://cdnjs.cloudflare.com/ajax/libs/p5.js/0.9.0/addons/p5.dom.min.js"></script> <script src="https://unpkg.com/ml5@latest/dist/ml5.min.js"></script> <script type="text/javascript"> // Classifier Variable let classifier; // Model URL let imageModelURL = 'https://teachablemachine.withgoogle.com/models/mR5N__d8O/';
// Video let video; let flippedVideo; // To store the classification let label = "";

// Load the model first function preload() { classifier = ml5.imageClassifier(imageModelURL + 'model.json'); }

function setup() { createCanvas(320, 260); // Create the video video = createCapture(VIDEO); video.size(320, 240); video.hide();

flippedVideo = ml5.flipImage(video);
// Start classifying
classifyVideo();
}

function draw() { background(0); // Draw the video image(flippedVideo, 0, 0);

// Draw the label
fill(255);
textSize(16);
textAlign(CENTER);
text(label, width / 2, height - 4);
}

// Get a prediction for the current video frame function classifyVideo() { flippedVideo = ml5.flipImage(video) classifier.classify(flippedVideo, gotResult); flippedVideo.remove();

}

// When we get a result function gotResult(error, results) { // If there is an error if (error) { console.error(error); return; } // The results are in an array ordered by confidence. // console.log(results[0]); label = results[0].label; // Classifiy again! classifyVideo(); } </script>
