<template>
  <div class="grounding">
    <div class="workspace">
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
        class="prop style">
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
        class="prop style">
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
        :class="{open: prop === 'assets'}"
        class="prop style">
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
        :class="{open: prop === 'layers'}"
        class="prop style">
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
        :class="{open: prop === 'build'}"
        class="prop style">
        <div
          @click="prop = 'build'"
          class="header">
          <h1>Build</h1>
        </div>
        <div class="body">
          Windows<br>
          Mac<br>
          Linux<br>
          Android<br>
          IOS<br>
          Web<br>
          WP Plugin<br>
          WP Theme
        </div>
      </div>
      <div
        :class="{open: prop === 'settings'}"
        class="prop style">
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
        :class="{open: prop === 'router'}"
        class="prop style">
        <div
          @click="prop = 'router'"
          class="header">
          <h1>Router</h1>
        </div>
        <div class="body">
          Hierarchial
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
  }
  .prop .header:hover {
    background: #333;
  }
  .prop .header h1, .prop h1.elem-header {
    padding: 10px;
    margin: 0;
    font-size: 12px;
    color: #bbb;
    border-bottom: 1px solid #000;
  }
  .prop h1.elem-header {
    display: inline-block;
    margin: 0!important;
    background: #eee;
    padding-left: 25px!important;
    font-size: 25px;
    font-weight: bold;
    width: 100%!important;
    color: #000;
    cursor: default!important;
    margin: 10px 0!important;
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