<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Teste - Front END - Leonardo Santos</title>
  <link ref='icon' href="%= BASE_URL %>favicon.ico">
  
      <!--Import Google Icon Font-->
      <link href="https://fonts.googleapis.com/icon?family=Material+Icons" rel="stylesheet">
      <!--Import materialize.css-->
      <!-- <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/materialize/1.0.0-rc.2/css/materialize.min.cs"> -->

  <head>

    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">
    <meta name="description" content="">
    <meta name="author" content="">
    <!-- <link rel="icon" href="/docs/4.0/assets/img/favicons/favicon.ico"> -->

    <title>Offcanvas template for Bootstrap</title>
    <link rel="canonical" href="https://getbootstrap.com/docs/4.0/examples/offcanvas/">
    <!-- Bootstrap core CSS -->
    <!-- <link href="integrity="sha384-Gn5384xqQ1aoWXA+058RXPxPg6fy4IWvTNh0E263XmFcJISAwiGgFAW/dAiS6JXm" crossorigin= anonymous"> -->
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css" integrity="sha384-Gn5384xqQ1aoWXA+058RXPxPg6fy4IWvTNh0E263XmFcJlSAwiGgFAW/dAiS6JXm" crossorigin="anonymous">


    <!-- Estilos personalizados para este modelo -->
    <!-- AQUI VOCE SÓ DEVE PASSAR ESSE TIPO DE CAMINHO QUANDO VOCÊ TIVER ALGUM CSS CONFIGURADO NA SUA PASTA -->
    <!-- <link href="offcanvas.css" rel="stylesheet"> -->
  </head>

  <body class="bg-light">
    <script
    src="https://code.jquery.com/jquery-3.5.1.min.js"
    integrity="sha256-9/aliU8dGd2tb6OSsuzixeV4y/faTqgFtohetphbbj0="
    crossorigin="anonymous"></script>


    <script>

      window.onload = function() { chamaapi() }
        function chamaapi() {
          $.ajax({
            url: 'http://dummy.restapiexample.com/api/v1/employees',
            method: 'get'
          })
          .done(function(obj) {
            var html = ''
            var html2 = ''
            var cores =  ['#1E90FF','#778899', '#20B2AA', '#006400', '#6B8E23', '#DEB887', '#7B68EE', '#A020F0', '#DDA0DD', '#FFA500', '#FFD700','#1E90FF','#778899', '#20B2AA', '#006400', '#6B8E23', '#DEB887', '#7B68EE', '#A020F0', '#DDA0DD', '#FFA500', '#FFD700','#1E90FF','#778899', '#20B2AA',   ]

            for (var i = 0; i < obj.data.length; i++) {
              html += "<div media text-muted pt-3>"
              html += "<div alt='32x32' class='mr-2 rounded' style='width: 32px; height: 32px; background-color:"+cores[i]+"; margin: 20px '  data-holder-rendered='true'> </div>"
              html += "<p class='media-body pb-3 mb-0 small lh-125 border-bottom border-gray'>"  
              html += '<strong class="d-block text-gray-dark">'+ obj.data[i].employee_name+ '</strong>'
              html += '</p>'
              html += '</div>'
              $('.div-pessoas').append(html);

            }

            for (var i = 0; i <obj.data.length; i ++) {
                html2 += '<div class="media text-muted pt-3">'
                html2 += '<div  data-holder-rendered="true" style="width: 32px; height: 32px; background-color:'+cores[i]+'; margin:20px"> </div>'
                html2 += '<div class="media-body pb-3 mb-0 small lh-125 border-bottom border-gray">'
                html2 += '<div class="d-flex justify-content-between align-items-center w-100">'
                html2 += '<strong class="text-gray-dark">' + obj.data[i].employee_name+ '</strong>'
                html2 += '<a href="#">Follow</a>'
                html2 += '</div>'
                html2 += '<span class="d-block">'+obj.data[i].employee_name+'</span>'
                html2 += '</div>'
                html2 += '</div>'
                $('.div-sujestoes').append(html2)
            }    
          })
          .fail(function() {
            alert("erro ao chamar a api")
          })
  
        }
  
      </script>
  

  
    <nav class="navbar navbar-expand-md fixed-top navbar-dark bg-dark">
      <a class="navbar-brand" href="#">Grupo Anima</a>
      <button class="navbar-toggler p-0 border-0" type="button" data-toggle="offcanvas">
        <span class="navbar-toggler-icon"></span>
      </button>

      <div class="navbar-collapse offcanvas-collapse" id="navbarsExampleDefault">
        <ul class="navbar-nav mr-auto">
          <li class="nav-item active">
            <a class="nav-link" href="#">
              painel de controle <span class="sr-only">(atual)</span></a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#">
              Notificações</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#">Perfil</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#">
              Mudar de conta</a>
          </li>
          <li class="nav-item dropdown">
            <a class="nav-link dropdown-toggle" href="http://example.com" id="dropdown01" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">Sugestões</a>
            <div class="dropdown-menu" aria-labelledby="dropdown01">
              <a class="dropdown-item" href="#">
                Açao</a>
              <a class="dropdown-item" href="#">Outra ação</a>
              <a class="dropdown-item" href="#">Algo mais aqui</a>
            </div>
          </li>
        </ul>
        <form class="form-inline my-2 my-lg-0">
          <input class="form-control mr-sm-2" type="text" placeholder="Pesquisar" aria-label="Pesquisar">
          <button class="btn btn-outline-success my-2 my-sm-0" type="submit">Pesquisar</button>
        </form>
      </div>
    </nav>

    <div class="nav-scroller bg-white box-shadow">
      <nav class="nav nav-underline">
        <a class="nav-link active" href="#">
          painel de controle</a>
        <a class="nav-link" href="#">
          Amigos
          <span class="badge badge-pill bg-light align-text-bottom">27</span>
        </a>
        <a class="nav-link" href="#">Explorar</a>
        <a class="nav-link" href="#">Sugestões</a>
        <a class="nav-link" href="#">Link</a>
        <a class="nav-link" href="#">Link</a>
        <a class="nav-link" href="#">Link</a>
        <a class="nav-link" href="#">Link</a>
        <a class="nav-link" href="#">Link</a>
      </nav>
    </div>

    <main role="main" class="container">
      <div class="d-flex align-items-center p-3 my-3 text-white-50 bg-purple rounded box-shadow">
        <img class="mr-3" src="https://getbootstrap.com/docs/4.0/assets/brand/bootstrap-outline.svg" alt="" width="48" height="48">
        <div class="lh-100">
          <h6 class="mb-0 text-white lh-100">Bootstrap</h6>
          <small>Teste 2020</small>
        </div>
      </div>

      <div class="my-3 p-3 bg-white rounded box-shadow">
        <h6 class="border-bottom border-gray pb-2 mb-0">
            Atualizações recentes</h6>

        <div class="div-pessoas"> <!-- vai ser carregada com o ajax (API )-->

        </div>

        <small class="d-block text-right mt-3">
          <a href="#">All updates</a>
        </small>
      </div>

      <div class="my-3 p-3 bg-white rounded box-shadow">
        <h6 class="border-bottom border-gray pb-2 mb-0">Sugestões</h6>
        
        <div class="div-sujestoes">  <!-- vai ser carregado com a api -->

        </div>

        <small class="d-block text-right mt-3">
          <a href="#">Todas as sugestões</a>
        </small>
      </div>
    </main>
</body>
    


