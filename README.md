# \<promise-dialog\>

**Promise-dialog** adds promises to
[**paper-dialog**](https://www.webcomponents.org/element/PolymerElements/paper-dialog)
that tell you when (and how) the user has dismissed a dialog.

[![Published on
webcomponents.org](https://img.shields.io/badge/webcomponents.org-published-blue.svg)](https://www.webcomponents.org/element/jonsmithers/promise-dialog)

## Quick Demo

<!---
```
<custom-element-demo>
  <template>
    <link rel="import" href="promise-dialog.html">
    <link rel="import" href="../paper-button/paper-button.html">
    <link rel="import" href="../paper-toast/paper-toast.html">
    <next-code-block></next-code-block>
  </template>
</custom-element-demo>
```
-->
```html
<script>
  function _onButtonClick() {

    promiseDialog.open().then(promiseValue => {

      toast.show({
        text: `Dialog has been dismissed. Promise resolved to "${promiseValue}"`
      });
    });
  }
</script>

<promise-dialog id="promiseDialog" modal>
  <h2>Title</h2>
  <div>
    body
  </div>
  <div class="buttons">
    <paper-button promise-reject>Reject dialog promise</paper-button>
    <paper-button promise-resolve promise-value="OK">Resolve dialog promise</paper-button>
  </div>
</promise-dialog>

<paper-button onclick="_onButtonClick()" raised style="margin:200px;">open promise dialog</paper-button>
<paper-toast id="toast"></paper-toast>
```
