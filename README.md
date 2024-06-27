<html lang="en">
  <head>
  <!-- Required meta tags -->
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">
    <!-- Bootstrap CSS -->
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@4.3.1/dist/css/bootstrap.min.css" integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T" crossorigin="anonymous">
    <link rel="stylesheet" href="readme.css">
  </head>

 <!-- Optional JavaScript - jQuery first, then Popper.js, then Bootstrap JS -->
    <script src="https://code.jquery.com/jquery-3.3.1.slim.min.js" integrity="sha384-q8i/X+965DzO0rT7abK41JStQIAqVgRVzpbzo5smXKp4YfRvH+8abtTE1Pi6jizo" crossorigin="anonymous"></script>
    <script src="https://cdn.jsdelivr.net/npm/popper.js@1.14.7/dist/umd/popper.min.js" integrity="sha384-UO2eT0CpHqdSJQ6hJty5KVphtPhzWj9WO1clHTMGa3JDZwrnQq4sF86dIHNDz0W1" crossorigin="anonymous"></script>
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@4.3.1/dist/js/bootstrap.min.js" integrity="sha384-JjSmVgyd0p3pXB1rRibZUAYoIIy6OrQ6VrjIEaFf/nJGzIxFDsf4x0xIM+B07jRM" crossorigin="anonymous"></script>

    <!-- Internal Functions -->
    <script type="text/javascript" src="readme.js"></script>


<form action="https://api.sheetmonkey.io/form/g3aoGDjR7AqXjmSyz4pkC6" method="post" class="needs-validation" novalidate>
  <div class="form-group row">
    <label class="col-sm-5" for="MEMBERSHIP">*Membership Number:</label>
    <label class="col-sm-6" style="margin-left:40px" for="CAR-REGISTRATION">*Car Registration:</label>
  </div>

  <div class="form-group row">
    <label style="padding-left:15px"></label>
    <input type="text" id="MEMBERSHIP" name="MEMBERSHIP" class="form-control col-sm-5" autocomplete="off" onkeyup="this.value = this.value.toUpperCase();" required>
    <input type="text" id="CAR-REGISTRATION" name="CAR-REGISTRATION" class="form-control col-sm-6" style="margin-left:30px" autocomplete="off" onkeyup="this.value = this.value.toUpperCase();" required>
  </div>

  <input type="datetime-local" id="ARRIVAL" name="ARRIVAL" class="form-control" autocomplete="off" required hidden>

  <div class="form-group">
    <label for="MODEL">Model (Optional):</label>
    <input type="text" id="MODEL" name="MODEL" class="form-control" autocomplete="off" style="text-transform: capitalize;">
  </div>  

  <div class="row g-2" style="margin-bottom:1rem">          
    <input class="form-check-input" type="checkbox" id="CONFIRMED" name="CONFIRMED" value="Yes" style="margin-left:15px" required>
    <label class="form-check-label col-md-11" for="CONFIRMED" style="word-wrap:break-word; margin-left:20px">
      I confirm that the vehicle registration information provided above is accurate. I understand that any inaccuracies may result in unauthorized parking and will lead to my vehicle being clamped.
    </label>
  </div>

  <!-- Button trigger modal -->
  <button type="button" class="btn btn-primary btn-lg btn-block" data-toggle="modal" data-target="#submitModal" onClick="submitText()">
       SUBMIT
  </button>

  <!-- Modal -->
  <div class="modal fade" id="submitModal">
    <div class="modal-dialog">
      <div class="modal-content">
        <div class="modal-header">
          <h4 class="modal-title" id="submitModalLabel">Please confirm your information!</h4>
          <button type="button" class="close" data-dismiss="modal" aria-label="Close">
            <span aria-hidden="true">&times;</span>
          </button>
        </div>
        <div class="modal-body" id="bodyModal">
        </div>
        <div class="modal-footer">
          <button type="button" class="btn btn-secondary btn-lg" data-dismiss="modal">Make Changes</button>
          <button type="submit" class="btn btn-primary btn-lg" data-toggle="modal" data-target="#submitModal">Confirm & Save</button>
        </div>
      </div>
    </div>
  </div>
</form>
</html>

<script>
function submitText(){        
        var html="Membership: <div class='font-weight-bold'>"+$("#MEMBERSHIP").val() + "</div>"
                  +"<br>Car Registration: <div class='font-weight-bold'>"+$("#CAR-REGISTRATION").val() + "</div>"
                  +"<br>Remarks: <div class='font-weight-bold'>"+$("#MODEL").val() + "</div>";
        $("#bodyModal").html(html);
}

//JavaScript for disabling form submissions if there are invalid fields
(function () {
  'use strict'

  // Fetch all the forms we want to apply custom Bootstrap validation styles to
  var forms = document.querySelectorAll('.needs-validation')

  // Loop over them and prevent submission
  Array.prototype.slice.call(forms)
    .forEach(function (form) {
      form.addEventListener('submit', function (event) {
        if (!form.checkValidity()) {
          event.preventDefault()
          event.stopPropagation()
        }

        form.classList.add('was-validated')
      }, false)
    })
})()
</script>
