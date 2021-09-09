## IINC/ | a Handshake(HNS) blockchain top level domain
[SHOP.IINC](http://shop.iinc.hns.to/) | [HNS-DOMAINS](http://home.hns-domains.hns.to/) | [🐻💻/](http://xn--gp8h6h.hns.to/)
[![image](https://user-images.githubusercontent.com/37987346/103435699-6be72500-4be0-11eb-8264-7dcb24c14987.png)](http://shapereality.innerinetcompany.hns.to/)



# The "I" of All-Conquering Spirit, the Omniscient, Omnipotent and Omnipresent Spark Within us is a drop of burning desire, rippling into a wave as The Great Awakening of the individual soul. Choose to awaken! NOW, presence a blaze, the All-Consuming Flame is seen as self-expression flowing from The Holy Spirit.

- [Inner I Net Company](https://shapereality.innerinetcompany.hns.to/) a [Handshake.org](https://handshake.org/) TLD.
- [Inner I Net Company](https://innerinetcompany.webflow.io/) on WebFlow.
- [Inner I Net Company](https://innerinetcompany.carrd.co/) on Carrd.
- [SHOP.Inner I NET COMPANY](http://shop.innerinetcompany.hns.to/)
- [INW](http://inw.hns.to/) 
- [IIK](http://iik.hns.to/)

# Channel within [#innerinet&company](https://webchat.hybridirc.com/#innerinet&company)
<iframe src="https://kiwiirc.hybridirc.com/#innerinet&company" allow="microphone; camera; display-capture; fullscreen" style="border:0; width:100%; height:500px;"></iframe>

<html>
  <body>
    <h1>Todos</h1>

    <ul></ul>

    <form><input><button>Add</button></form>

    <script src="https://cdn.jsdelivr.net/npm/gun/gun.js"></script>
    <script src="https://code.jquery.com/jquery-1.12.4.min.js"></script>
    <script>
      var todos = Gun().get('todos')

      $('form').on('submit', function (event) {
        var input = $('form').find('input')
        todos.set({title: input.val()})
        input.val('')
        event.preventDefault()
      })

      todos.map().on(function (todo, id) {
        var li = $('#' + id)
        if (!li.get(0)) {
          li = $('<li>').attr('id', id).appendTo('ul')
        }
        if (todo) {
          var html = '<span onclick="clickTitle(this)">' + todo.title + '</span>'
          html = '<input type="checkbox" onclick="clickCheck(this)" ' + (todo.done ? 'checked' : '') + '>' + html
          html += '<img onclick="clickDelete(this)" src="https://cdnjs.cloudflare.com/ajax/libs/foundicons/3.0.0/svgs/fi-x.svg"/>'
          li.html(html)
        } else {
          li.remove()
        }
      })
      function clickTitle (element) {
        element = $(element)
        if (!element.find('input').get(0)) {
          element.html('<input value="' + element.html() + '" onkeyup="keypressTitle(this)">')
        }
      }

      function keypressTitle (element) {
        if (event.keyCode === 13) {
          todos.get($(element).parent().parent().attr('id')).put({title: $(element).val()})
        }
      }
      
      function clickCheck (element) {
        todos.get($(element).parent().attr('id')).put({done: $(element).prop('checked')})
      }

      function clickDelete (element) {
        todos.get($(element).parent().attr('id')).put(null)
      }
    </script>
    
    <html>
  <body>
    <h1>Todo</h1>

    <form id="sign">
      <input id="alias" placeholder="username">
      <input id="pass" type="password" placeholder="passphrase">
      <input id="in" type="submit" value="sign in">
      <input id="up" type="button" value="sign up">
    </form>

    <ul></ul>

    <form id="said">
        <input id="say">
        <input id="speak" type="submit" value="speak">
    </form>

    <script src="https://cdn.jsdelivr.net/npm/gun/examples/jquery.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/gun/gun.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/gun/sea.js"></script>
    <!-- script src="https://cdn.jsdelivr.net/npm/gun/lib/webrtc.js"></script -->
    <script>
    var gun = Gun(['http://localhost:8765/gun', 'https://mvp-gun.herokuapp.com/gun', 'https://e2eec.herokuapp.com/gun']);
    var user = gun.user();

    $('#up').on('click', function(e){
      user.create($('#alias').val(), $('#pass').val());
    });

    $('#sign').on('submit', function(e){
      e.preventDefault();
      user.auth($('#alias').val(), $('#pass').val());
    });

    $('#said').on('submit', function(e){
      e.preventDefault();
      if(!user.is){ return }
      user.get('said').set($('#say').val());
     
  
