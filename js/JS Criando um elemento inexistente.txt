$(document).ready(function() {
    $('header button').click(function() {
      $('form').slideDown();
    });
  
    $('#cancel').click(function() {
      $('form').slideUp();
    });
  
    $('form').on('submit', function(e) {
      e.preventDefault();
  
      var imageUrl = $('input[type="url"]').val();
  
      var listItem = $('<li>'); // Cria um novo elemento <li>
      var image = $('<img>').attr('src', imageUrl); // Cria a tag <img> e define o atributo "src"
      var overlayLink = $('<div>').addClass('overlay-img-link'); // Cria um elemento <div> com a classe "overlay-img-link"
      var link = $('<a>').attr('href', imageUrl).attr('target', '_blank').text('ver imagem em tamanho real'); // Cria a tag <a> e define os atributos e texto
  
      overlayLink.append(link); // Adiciona o link à div "overlay-img-link"
      listItem.append(image).append(overlayLink); // Adiciona a imagem e a div à nova <li>
  
      $('ul').prepend(listItem); // Insere a nova <li> no início da lista
  
      $('input[type="url"]').val('');
      /*$('form').slideUp();*/
    });
  });
  