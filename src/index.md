# Table with problem

<button id="change-table-layout">current style -- >> CLICK ME <<</button>

<div markdown="1" class="explicit-col-width">

| Parameter                                          | Type   | Default                        | Description                                                                                                                                                                                                                                                                                                                                                                             |
|:---------------------------------------------------|:-------|:-------------------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `abc`                                              | int    | `0`                            | Lorem ipsum dolor sit amet, consectetur adipisicing elit. Nam, enim?                                                                                                                                                                                                                                                                                                                    |
| `longer_param_name`                                | regex  | `s/cat/dog/i`                  | Lorem ipsum dolor sit amet, consectetur adipisicing elit. Facilis nemo vitae cumque! Sit quibusdam obcaecati aut, sed odio assumenda soluta eum! Nesciunt repellendus eaque delectus, nemo, aperiam laudantium ipsam rem.                                                                                                                                                               |
| `some_another_parameter_name_that_is_even_longer`  | path   | `long/path_to_some_foo_bar_baz_foo_bar_baz_file.txt`  | Lorem ipsum dolor sit amet, consectetur adipisicing elit. Tenetur exercitationem quas ducimus quos quaerat, adipisci illo nobis odio aut rem amet quibusdam debitis, error repudiandae modi consequatur ratione ad optio totam minus sequi ut maxime. Saepe aliquam tempore quibusdam, eum voluptas suscipit. Porro exercitationem quae harum vero, perspiciatis, consectetur ratione.  |

</div>

## Welcome to MkDocs

For full documentation visit [mkdocs.org](https://mkdocs.org).

## Commands

* `mkdocs new [dir-name]` - Create a new project.
* `mkdocs serve` - Start the live-reloading docs server.
* `mkdocs build` - Build the documentation site.
* `mkdocs help` - Print this help message.

## Project layout

    mkdocs.yml    # The configuration file.
    docs/
        index.md  # The documentation homepage.
        ...       # Other markdown pages, images and other files.

<script type='text/javascript'>
function changeTableLayout() { 
  let t = document.evaluate("//div[contains(@class, 'md-typeset__table')]/table", document, null, XPathResult.FIRST_ORDERED_NODE_TYPE, null).singleNodeValue;
  const style = t.getAttribute('style');

  if (style === "table-layout:fixed") {
    t.setAttribute('style', 'table-layout:auto');  
  }
  else if (style === "table-layout:auto") {
    t.setAttribute('style', 'table-layout:fixed');  
  }
  else {
    t.setAttribute('style', 'table-layout:fixed'); 
  }
  updateButtonText();
}

function updateButtonText() {
  let b = document.getElementById('change-table-layout')
  const t = document.evaluate("//div[contains(@class, 'md-typeset__table')]/table", document, null, XPathResult.FIRST_ORDERED_NODE_TYPE, null).singleNodeValue;
  const style = t.getAttribute('style');
  b.textContent = 'current style -- ' + style;
}

b = document.getElementById('change-table-layout')
document.getElementById('change-table-layout').onclick = changeTableLayout;
</script>
