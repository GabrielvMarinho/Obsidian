How to do a Drag n Drop using puer [[Javascript]]

index.html
```
<div class="dropzone">Dropzone 1</div>
<div class="dropzone">Dropzone 2</div>
<div class="dropzone">Dropzone 3</div>

<div class="draggable" id="item1" draggable="true">Item 1</div>
<div class="draggable" id="item2" draggable="true">Item 2</div>
<div class="draggable" id="item3" draggable="true">Item 3</div>

```

script.js
```
const draggables = document.querySelectorAll('.draggable');
const dropzones = document.querySelectorAll('.dropzone');


draggables.forEach(draggable => {
  draggable.addEventListener('dragstart', (event) => {
    event.dataTransfer.setData('text/plain', event.target.id);
    draggable.classList.add('dragging');
  });

  draggable.addEventListener('dragend', () => {
    draggable.classList.remove('dragging');
  });
});

dropzones.forEach(dropzone => {
  dropzone.addEventListener('dragenter', (event) => {
    event.preventDefault();
    dropzone.classList.add('over');
  });

  dropzone.addEventListener('dragover', (event) => {
    event.preventDefault();
  });

  dropzone.addEventListener('dragleave', () => {
    dropzone.classList.remove('over');
  });

  dropzone.addEventListener('drop', (event) => {
    event.preventDefault();
    const draggableId = event.dataTransfer.getData('text/plain');
    const draggable = document.getElementById(draggableId);
    dropzone.classList.remove('over');
    dropzone.appendChild(draggable); // Move o elemento para a área de drop
  });
});

```