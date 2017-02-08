<ul class="shots"></ul>

  <script src="bower_components/jquery/dist/jquery.min.js"></script>
  <script src="bower_components/jribbble/dist/jribbble.min.js"></script>

  <script>
    $.jribbble.setToken('1234567890');

    /*
      Jribbble methods make ajax requests to the Dribbble API. When
      the requests complete, a Promise is returned. Use `then` to take an action
      on the response from the server.
    */
    $.jribbble.shots('teams').then(function(shots) {
      var html = [];

      shots.forEach(function(shot) {
        // See the Dribbble docs for all available shot properties.
        html.push('<li class="shots--shot">');
        html.push('<a href="' + shot.html_url + '">');
        html.push('<img src="' + shot.images.normal + '">');
        html.push('</a></li>');
      });

      $('.shots').html(html.join(''));
    });
  </script>
