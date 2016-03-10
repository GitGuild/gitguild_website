+++
weight = 3
title = "Contact Us"
topMenu = true
+++

<form action='https://crm.zoho.com/crm/WebToLeadForm'
      name=WebToLeads1729302000000110005 method='POST'
      onSubmit='return checkMandatory()'
      accept-charset='UTF-8'>

  <!-- Required internal fields. -->
  <input type='text' style='display:none;' name='xnQsjsdp' value='d3b1137b095581ac2be866e9362c6bfc11145c48a5400dfa6fa30f2d967cfd47'/>
  <input type='hidden' name='zc_gad' id='zc_gad' value=''/>
  <input type='text' style='display:none;' name='xmIwtLD' value='be71074d0bfc53517421f4618a1d4dd475cb7cbfe70d9e4ca13467b7e27c9a54'/>
  <input type='text' style='display:none;'  name='actionType' value='TGVhZHM='/>
  <input type='text' style='display:none;' name='returnURL' value='{{% baseurl %}}' />
   <!-- Required internal fields. -->

  <div class="form-row">
    <label for="firstname">Name
      <span class="form-error" id="error-name">Please specify your name</span>
    </label>
    <div class="form-half-row" style="padding-right: 2%">
      <input type="text" maxlength="40" name="First Name" id="firstname"
          placeholder="First">
    </div><div class="form-half-row">
      <input type="text" maxlength="80" name="Last Name" id="lastname"
          placeholder="Last">
    </div>
  </div>

  <div class="form-row">
    <label for="email">Email
      <span class="form-error" id="error-email">
        Please specify your email so we can communicate with you
      </span>
    </label>
    <input type="text" maxlength="100" name="Email" id="email">
  </div>

  <div class="form-row">
    <label for="company">Company <span class="contact-info">optional</span></label>
    <input type="text" maxlength="100" name="Company" id="company">
  </div>

  <div class="form-row">
    <label for="message">Message
      <span class="form-error" id="error-message">
        We will need some message to know what you are after
      </span>
    </label>
    <textarea name="Description" id="message" cols="40" rows="10" maxlength="1000"></textarea>
  </div>

  <div class="form-align">
    <input type="submit" value="Send">
    <span class="contact-info">You will receive a copy of this contact
request.</span>
  </div>

  <script>
    var fields = ['firstname', 'lastname', 'email', 'message'];
    var basicEmail = /^[^ @]+@([^ @]+){2,}\.([^ @]+){2,}$/;

    function checkMandatory() {
      /* Hide any errors. */
      var allErrors = document.getElementsByClassName('form-error');
      for (var i = 0; i < allErrors.length; i++) {
        allErrors[i].style.display = 'none';
      }

      /* Validate the form. */
      var form = document.forms['WebToLeads1729302000000110005'];
      for (var i = 0; i < fields.length; i++) {
        var fieldObj = form[fields[i]];
        if (fieldObj) {
          var failed = fieldObj.value.replace(/^\s+|\s+$/g, '').length === 0;
          if (!failed && fields[i] === 'email') {
            failed = !basicEmail.test(fieldObj.value);
          }

          if (failed) {
            fieldObj.focus();
            var name = fields[i];
            if (name.endsWith('name')) {
              name = 'name';
            }
            var err = document.getElementById('error-' + name);
            if (err) {
              err.style.display = 'block';
            }
            return false;
          }
        }
      }
    }
  </script>
</form>
