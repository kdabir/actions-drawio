# actions-drawio ![CI Tests](https://github.com/Burnett01/actions-drawio/workflows/CI%20Tests/badge.svg)

Convert draw.io compressed XML-documents to ``jpeg|png|svg|pdf`` using [drawio-batch](https://github.com/languitar/drawio-batch).

This action makes use of the heavily optimized Docker image [(alpine-drawio-batch)](https://github.com/Burnett01/docker-images/tree/alpine-drawio-batch).

---

## Usage

You can run this action by using the ``with:`` block

```yml
  steps:
  - uses: actions/checkout@v2
  - name: Convert digramm to png
    uses: Burnett01/actions-drawio@1.2
    with:
      src: diagramm.drawio
      dest: diagramm.png
```

**Inputs**

+ ``quality`` The quality for png & jpeg (eg. 100)

+ ``scale`` The scale (eg. 1.0)

+ ``src`` The source file (eg. input.drawio)

+ ``dest`` The destination file (eg. output.jpeg)

---

## Combinations

You can combine this actions with other ones, such as [upload-artifact](https://github.com/actions/upload-artifact):

```yml
steps:
    - uses: actions/checkout@v2
    - name: Convert test file to png image
      uses: Burnett01/actions-drawio@1.2
      with:
        src: test.drawio
        dest: test.png
    - name: Upload image as artifact
      uses: actions/upload-artifact@v1
      with:
        name: png
        path: test.png
```

---

## Note

If you are using uncompressed drawio XML documents, this action will not work.<br />
The underlaying module only supports compressed XML-documents.

Thus, you will have to export your draw.io XML document as "compressed".

[Check out this post to see how this is one.](https://github.com/Burnett01/actions-drawio/issues/1#issuecomment-830344814)

---

## Demo/Tests

Check the Actions tab for a live demo:

[Live Demo](https://github.com/Burnett01/actions-drawio/actions?query=workflow%3A%22CI+Tests%22)

<img src="https://i.imgur.com/yvsjy2P.png" />     

