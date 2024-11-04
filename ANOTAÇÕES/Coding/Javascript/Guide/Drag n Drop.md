index.html
```
<div class="container"> 
	<div class="draggable" draggable="true">Arraste-me!</div> 
	<div class="dropzone">Solte Aqui</div> 
</div>
```

script.js
```
const draggable = document.querySelector('.draggable');

const dropzone = document.querySelector('.dropzone');

// Evento dragstart - inicia o arrasto do elemento

draggable.addEventListener('dragstart', (event) => {

  event.dataTransfer.setData('text/plain', event.target.id);

  draggable.classList.add('dragging'); // Adiciona uma classe de estilo enquanto arrasta

});

  

// Evento dragend - finaliza o arrasto

draggable.addEventListener('dragend', () => {

  draggable.classList.remove('dragging');

});

  

// Evento dragenter - elemento entra na área de drop

dropzone.addEventListener('dragenter', (event) => {

  event.preventDefault();

  dropzone.classList.add('over');

});

  

// Evento dragover - elemento está sobre a área de drop

dropzone.addEventListener('dragover', (event) => {

  event.preventDefault(); // Necessário para permitir o drop

});

  

// Evento dragleave - elemento deixa a área de drop

dropzone.addEventListener('dragleave', () => {

  dropzone.classList.remove('over');
});

  

// Evento drop - elemento é solto na área de drop

dropzone.addEventListener('drop', (event) => {

  event.preventDefault();

  dropzone.classList.remove('over');

  dropzone.appendChild(draggable); // Move o elemento arrastável para dentro da área de drop

});
```