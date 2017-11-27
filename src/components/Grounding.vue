<template>
  <div class="grounding">
    <div class="workspace">
      <div class="view">
      </div>
    </div>
    <div v-if="editor" class="tools">
      <div
        @click="tool = 'select'"
        :class="{selected: tool === 'select'}"
        class="tool select">
      </div>
      <div
        @click="tool = 'move'"
        :class="{selected: tool === 'move'}"
        class="tool move">
      </div>
    </div>
    <div v-if="editor" class="props">
      <div
        :class="{open: prop === 'style'}"
        class="prop">
        <div
          @click="prop = 'style'"
          class="header">
          <h1>Style</h1>
        </div>
        <div class="body">
          Color<br>
          Position<br>
          Size etc. (css)
        </div>
      </div>
      <div
        :class="{open: prop === 'elements'}"
        class="prop elements">
        <div
          @click="prop = 'elements'"
          class="header">
          <h1>Elements</h1>
        </div>
        <div class="body elements">
          <h1 class="elem-header">Text Content</h1>
          <div>Div</div>
          <blockquote>Blockquote</blockquote>
          <dl>Description List</dl>
          <dt>Description Term</dt>
          <dd>Description Term Content</dd>
          <hr>
          <figure>Figure</figure>
          <figcaption>Figure Caption</figcaption>
          <main>Main Content</main>
          <p>Paragraph</p>
          <pre>Preformatted</pre>
          <ul>List</ul>
          <ol>List Numbered</ol>
          <li>List Element</li>
          <h1 class="elem-header">Text Inline</h1>
          <a>Link</a>
          <bdi>Biderectional Isolation</bdi>
          <bdo>Biderectional Override</bdo>
          <br>
          <cite>Creative Work</cite>
          <code>Code</code>
          <data>Data</data>
          <dfn>Term defination Instance</dfn>
          <em>Stress Emphasis</em>
          <pre>Preformatted</pre>
          <kbd>User Input</kbd>
          <span>Text</span>
          <mark>Highlighted</mark>
          <q>Short Inline Quote</q>
          <b>Bold</b>
          <i>Italic</i>
          <u>Underline</u>
          <s>Strikethrough</s>
          <ruby>Ruby (East Asian Chars)</ruby>
          <rt>Ruby Pronunciation</rt>
          <rtc>Ruby Semantic Annotations</rtc>
          <rp>Ruby Fallback</rp>
          <samp>Sample</samp>
          <small>Small</small>
          <strong>Strong</strong>
          <sub>Text Low</sub>
          <sup>Text High</sup>
          <time>Time</time>
          <var>Variable</var>
          <wbdr>Line Break</wbdr>
          <h1 class="elem-header">Multimedia</h1>
          <area>Image Hotspot</area>
          <audio>Audio</audio>
          <video>Video</video>
          <track>
          <picture>Picture</picture>
          <h1 class="elem-header">Embedded</h1>
          <embed>Embed</embed>
          <object>Object</object>
          <param>Object Parameter</param>
          <source>Source</source>
          <h1 class="elem-header">Scripting</h1>
          <canvas>Canvas</canvas>
          <noscript>No Script</noscript>
          <h1 class="elem-header">Demarcating Edits</h1>
          <del>Deleted</del>
          <ins>Inserted</ins>
          <h1 class="elem-header">Table</h1>
          <caption>Caption</caption>
          <table>Table</table>
          <tbody>Body</tbody>
          <tfoot>Footer</tfoot>
          <thead>Header</thead>
          <tr>Row</tr>
          <td>Cell</td>
          <th>Cell header</th>
          <colgroup>Column Group</colgroup>
          <col>Column</col>
          <h1 class="elem-header">Forms</h1>
          <button>Button</button>
          <datalist>Datalist</datalist>
          <Fieldset>Fieldset</Fieldset>
          <Legend>Legend</Legend>
          <form>Form</form>
          <input>Input</input>
          <label>Label</label>
          <meter>Meter</meter>
          <optgroup>Option Group</optgroup>
          <option>Option</option>
          <output>Output</output>
          <progress>Progress</progress>
          <select>Select</select>
          <textarea></textarea>
          <h1 class="elem-header">Interactive</h1>
          <details>Details</details>
          <dialog>Dialog</dialog>
          <menu>Menu</menu>
          <menuitem>Menu Item</menuitem>
          <summary>Summary</summary>
          <h1 class="elem-header">Web</h1>
          <content>Content</content>
          <element>Element</element>
          <shadow>Shadow</shadow>
          <slot>Slot</slot>
          <template>Template</template>
          <iframe>Iframe</iframe>
          <h1 class="elem-header">Content Sectioning</h1>
          <h1>Header 1</h1>
          <h2>Header 2</h2>
          <h3>Header 3</h3>
          <h4>Header 4</h4>
          <h5>Header 5</h5>
          <h6>Header 6</h6>
          <address>Address</address>
          <article>Article</article>
          <aside>Sidebar</aside>
          <header>Header</header>
          <footer>Footer</footer>
          <nav>Navigator</nav>
          <section>Section</section>
        </div>
      </div>
      <div
        :class="{open: prop === 'events'}"
        class="prop">
        <div
          @click="prop = 'events'"
          class="header">
          <h1>Events</h1>
        </div>
        <div class="body">
          Elemental<br>
          Global
        </div>
      </div>
      <div
        :class="{open: prop === 'layers'}"
        class="prop">
        <div
          @click="prop = 'layers'"
          class="header">
          <h1>Layers</h1>
        </div>
        <div class="body">
          DOM Tree
        </div>
      </div>
      <div
        :class="{open: prop === 'assets'}"
        class="prop">
        <div
          @click="prop = 'assets'"
          class="header">
          <h1>Assets</h1>
        </div>
        <div class="body">
          File Explorer
        </div>
      </div>
      <div
        :class="{open: prop === 'context'}"
        class="prop">
        <div
          @click="prop = 'context'"
          class="header">
          <h1>Context Menu</h1>
        </div>
        <div class="body">
          Option 1<br>
          Option 2<br>
          Option 3
        </div>
      </div>
      <div
        :class="{open: prop === 'models'}"
        class="prop">
        <div
          @click="prop = 'models'"
          class="header">
          <h1>Models</h1>
        </div>
        <div class="body">
          (Folder structure)<br>
          Product<br>
          Car<br>
          Pencil<br>
          User<br>
        </div>
      </div>
      <div
        :class="{open: prop === 'pages'}"
        class="prop">
        <div
          @click="prop = 'pages'"
          class="header">
          <h1>Pages</h1>
        </div>
        <div class="body">
          (Folder structure)<br>
          Page 1<br>
          Page 2
        </div>
      </div>
      <div
        :class="{open: prop === 'routes'}"
        class="prop">
        <div
          @click="prop = 'routes'"
          class="header">
          <h1>Routes</h1>
        </div>
        <div class="body">
          Route 1<br>
          Route 2
        </div>
      </div>
      <div
        :class="{open: prop === 'menu'}"
        class="prop">
        <div
          @click="prop = 'menu'"
          class="header">
          <h1>Native Menu</h1>
        </div>
        <div class="body">
          Item 1<br>
          Item 2
        </div>
      </div>
      <div
        :class="{open: prop === 'database'}"
        class="prop">
        <div
          @click="prop = 'database'"
          class="header">
          <h1>Database</h1>
        </div>
        <div class="body">
          Table 1<br>
          Table 2<br>
          Table 3<br>
        </div>
      </div>
      <div
        :class="{open: prop === 'integrations'}"
        class="prop">
        <div
          @click="prop = 'integrations'"
          class="header">
          <h1>Integrations</h1>
        </div>
        <div class="body">
          (New opens papir settings)<br>
          Wordpress<br>
          Woocommerce<br>
          Storepilot
        </div>
      </div>
      <div
        :class="{open: prop === 'packages'}"
        class="prop">
        <div
          @click="prop = 'packages'"
          class="header">
          <h1>Packages</h1>
        </div>
        <div class="body">
          (From package json)<br>
          Element-UI<br>
          Bootstrap<br>
          Context Menu<br>
        </div>
      </div>
      <div
        :class="{open: prop === 'settings'}"
        class="prop">
        <div
          @click="prop = 'settings'"
          class="header">
          <h1>Settings</h1>
        </div>
        <div class="body">
          Icon<br>
          Window width<br>
          Window height<br>
          Window position<br>
          Allow resize<br>
          IOS Default scroll<br>
        </div>
      </div>
      <div
        :class="{open: prop === 'revision'}"
        class="prop">
        <div
          @click="prop = 'revision'"
          class="header">
          <h1>History</h1>
        </div>
        <div class="body">
          Commit 5<br>
          Commit 4<br>
          Commit 3<br>
        </div>
      </div>
      <div
        :class="{open: prop === 'export'}"
        class="prop">
        <div
          @click="prop = 'export'"
          class="header">
          <h1>Export</h1>
        </div>
        <div class="body">
          Project<br>
          Windows App<br>
          Mac App<br>
          Linux App<br>
          Android App<br>
          IOS App<br>
          Web Page<br>
          Wordpress Plugin<br>
          Wordpress Theme
        </div>
      </div>
    </div>
    <div class="devbar">
      <div
        @click="editor = !editor"
        :class="{'editor-open': editor}"
        class="toggl">
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'grounding',
    data () {
      return {
        editor: true,
        tool: 'move',
        prop: 'elements-text'
      }
    }
  }
</script>

<style>
  .grounding {
    width: 100%;
    height: 100%;
  }
  .workspace {
    position: absolute;
    width: 100%;
    height: calc(100% - 26px);
    background: #333;
  }
  .view {
    position: relative;
    margin: 30px auto;
    width: calc(100vh / 2);
    height: calc(100vh - 60px - 26px);
    background: #000;
  }
  .devbar {
    position: absolute;
    bottom: 0;
    height: 26px;
    width: 100%;
    background: #444;
  }
  .toggl {
    position: absolute;
    bottom: 3px;
    left: 3px;
    width: 20px;
    height: 20px;
    background: #fff;
    opacity: .2;
    border-radius: 3px;
  }
  .toggl:hover {
    opacity: .7;
    cursor: pointer;
  }
  .tools {
    position: absolute;
    width: 26px;
    height: calc(100% - 26px);
    background: #444;
  }
  .tool {
    color: #ccc;
    position: relative;
    width: 100%;
    height: 28px;
    background: #222;
    border-bottom: 1px solid #000;
  }
  .tool:hover {
    background: #555;
    cursor: pointer;
  }
  .tool.selected, .tool.selected:hover {
    background: #888;
  }
  .props {
    position: absolute;
    right: 0;
    width: 200px;
    height: calc(100% - 26px);
    background: #444;
    border-bottom: 1px solid #333;
    overflow-y: scroll;
    overflow-x: hidden;
  }
  .prop .header, .prop .elem-header {
    cursor: pointer;
    background: #222;
    opacity: 1!important;
  }
  .prop .header:hover {
    background: #333;
  }
  .prop .header h1, .prop h1.elem-header {
    padding: 10px;
    margin: 0;
    font-size: 12px;
    color: #ccc;
    border-bottom: 1px solid #000;
  }
  .prop h1.elem-header {
    display: inline-block;
    padding-left: 25px!important;
    background: #000;
    font-size: 25px;
    font-weight: bold;
    width: 100%!important;
    cursor: default!important;
    margin: 0 0 10px!important;
  }
  .prop .body {
    display: none;
  }
  .prop.open .body {
    display: block;
    color: #ddd;
  }
  .prop.open .body.elements * {
    display: block;
    padding: 5px;
    width: calc(100% - 10px);
    margin: 0 5px 5px;
  }
  .prop.open .body.elements h1,
  .prop.open .body.elements h2,
  .prop.open .body.elements h3,
  .prop.open .body.elements h4,
  .prop.open .body.elements h5,
  .prop.open .body.elements h6{
    zoom: 50%;
  }
  .prop.open .body.elements *:nth-child(2n) {
    opacity: .7;
  }
</style>