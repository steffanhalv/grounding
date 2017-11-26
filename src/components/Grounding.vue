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
          Styles
        </div>
      </div>
      <div
        :class="{open: prop === 'elements-text'}"
        class="prop elements">
        <div
          @click="prop = 'elements-text'"
          class="header">
          <h1>Text Content</h1>
        </div>
        <div class="body elements">
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
        </div>
      </div>
      <div
        :class="{open: prop === 'elements-text-inline'}"
        class="prop elements">
        <div
          @click="prop = 'elements-text-inline'"
          class="header">
          <h1>Text Inline</h1>
        </div>
        <div class="body elements">
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
        </div>
      </div>
      <div
        :class="{open: prop === 'elements-media'}"
        class="prop elements">
        <div
          @click="prop = 'elements-media'"
          class="header">
          <h1>Multimedia</h1>
        </div>
        <div class="body elements">
          <area>Image Hotspot</area>
          <audio>Audio</audio>
          <video>Video</video>
          <track>
          <picture>Picture</picture>
        </div>
      </div>
      <div
        :class="{open: prop === 'elements-embeded'}"
        class="prop elements">
        <div
          @click="prop = 'elements-embeded'"
          class="header">
          <h1>Embedded</h1>
        </div>
        <div class="body elements">
          <embed>Embed</embed>
          <object>Object</object>
          <param>Object Parameter</param>
          <source>Source</source>
        </div>
      </div>
      <div
        :class="{open: prop === 'elements-scripting'}"
        class="prop elements">
        <div
          @click="prop = 'elements-scripting'"
          class="header">
          <h1>Scripting</h1>
        </div>
        <div class="body elements">
          <canvas>Canvas</canvas>
          <noscript>No Script</noscript>
        </div>
      </div>
      <div
        :class="{open: prop === 'elements-demarc'}"
        class="prop elements">
        <div
          @click="prop = 'elements-demarc'"
          class="header">
          <h1>Demarcating Edits</h1>
        </div>
        <div class="body elements">
          <del>Deleted</del>
          <ins>Inserted</ins>
        </div>
      </div>
      <div
        :class="{open: prop === 'elements-table'}"
        class="prop elements">
        <div
          @click="prop = 'elements-table'"
          class="header">
          <h1>Table</h1>
        </div>
        <div class="body elements">
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
        </div>
      </div>
      <div
        :class="{open: prop === 'elements-forms'}"
        class="prop elements">
        <div
          @click="prop = 'elements-forms'"
          class="header">
          <h1>Forms</h1>
        </div>
        <div class="body elements">
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
        </div>
      </div>
      <div
        :class="{open: prop === 'elements-interactive'}"
        class="prop elements">
        <div
          @click="prop = 'elements-interactive'"
          class="header">
          <h1>Interactive</h1>
        </div>
        <div class="body elements">
          <details>Details</details>
          <dialog>Dialog</dialog>
          <menu>Menu</menu>
          <menuitem>Menu Item</menuitem>
          <summary>Summary</summary>
        </div>
      </div>
      <div
        :class="{open: prop === 'elements-web'}"
        class="prop elements">
        <div
          @click="prop = 'elements-web'"
          class="header">
          <h1>Web</h1>
        </div>
        <div class="body elements">
          <content>Content</content>
          <element>Element</element>
          <shadow>Shadow</shadow>
          <slot>Slot</slot>
          <template>Template</template>
          <iframe>Iframe</iframe>
        </div>
      </div>
      <div
        :class="{open: prop === 'elements-content'}"
        class="prop elements">
        <div
          @click="prop = 'elements-content'"
          class="header">
          <h1>Content Sectioning</h1>
        </div>
        <div class="body elements">
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
    </div>
    <div
      @click="editor = !editor"
      :class="{'editor-open': editor}"
      class="toggl">
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
    height: 100%;
    background: #333;
  }
  .toggl {
    position: absolute;
    bottom: 8px;
    left: 8px;
    width: 20px;
    height: 20px;
    background: #000;
    opacity: .2;
    border-radius: 3px;
  }
  .toggl.editor-open {
    background: #fff;
  }
  .toggl:hover {
    opacity: .7;
    cursor: pointer;
  }
  .tools {
    position: absolute;
    width: 34px;
    height: 100%;
    background: #444;
  }
  .tool {
    color: #ccc;
    position: relative;
    width: 100%;
    height: 34px;
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
    height: 100%;
    background: #444;
    overflow-y: scroll;
    overflow-x: hidden;
  }
  .prop .header {
    cursor: pointer;
    background: #222;
  }
  .prop .header:hover {
    background: #333;
  }
  .prop .header h1 {
    padding: 5px;
    margin: 0;
    font-size: 12px;
    color: #bbb;
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