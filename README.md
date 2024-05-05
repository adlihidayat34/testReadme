<h1>n<span style="color: red;">ew h1</span></h1>

<h3 class="ql-align-center">ne<sub>w h</sub>3<sub><span class="ql-cursor">﻿</span></sub></h3>

<h2 class="ql-align-center">new h2</h2>

<h4>new h4</h4>

<p>ne<sup>w p<span class="ql-cursor">﻿</span></sup></p>

<p class="ql-align-center">												n<strong>ew</strong> pq<em>wdas </em>das<s> dAWf</s> a<u>fawq </u><span style="background-color: white;">fasfegaw</span> <u>fasfw</u></p><ol><li>afsaf</li></ol><p>asdas</p><p>	I started in 2009 with HTML and CSS, making simple static web pages and expanding my knowledge over time. Around 2010/2011, I started to learn how to use JavaScript to create dynamic web apps. During this time I also learned a version of BASIC so I could program games for my 3DS using a DSi app called Petit Computer. In 2015 I found NodeJS and started using it to create some basic bots for various chat platforms.</p>

<p>new p</p>


const downloadReadme = () => {
  // Helper function to convert Quill's alignment classes to HTML align attributes
  const convertAlignment = (html: string) => {
    const regex = /class="ql-align-(left|center|right)"/g;
    return html.replace(regex, (match, alignment) => {
      return `align="${alignment}"`;
    });
  };

  // Convert alignments and concatenate the content of each item
  const markdownContent = readme
    .map((item: any) => convertAlignment(item.content))
    .join("\n\n");

  // Create a Blob containing the Markdown content
  const blob = new Blob([markdownContent], { type: "text/plain" });

  // Create a URL for the Blob
  const url = URL.createObjectURL(blob);

  // Create a link with download attribute
  const link = document.createElement("a");
  link.href = url;
  link.download = "readme.md";

  // Trigger a click event on the link to initiate the download
  link.click();

  // Cleanup: Revoke the URL object to free up resources
  URL.revokeObjectURL(url);
};
