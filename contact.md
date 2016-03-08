---
layout: page
title: Contact us
permalink: /contact/
---

<div class="row mar-top-50">
    <form action="http://kodeplay.us1.list-manage2.com/subscribe/post" method="POST" id="form" class="col s12">
    <input type="hidden" name="u" value="6e6b97bcec6ff8a7445db3971">
    <input type="hidden" name="id" value="4d6ccc6413">
    <!--
    <form class="col s12" action="" method="POST">
    -->
      <div class="row">
        <div class="input-field col s6 pad20">
          <input name="FNAME" id="first_name" type="text" class="validate">
          <label for="FNAME" class="standard_font_estimate">Full Name</label>
          <div id="first_name_e" style="color:red;"></div>
        </div>
        <div class="input-field col s6 pad20">
          <input id="email" name="EMAIL" type="email" class="validate">
          <label for="EMAIL" class="standard_font_estimate">Email</label>
          <div id="email_e" style="color:red;"></div>
        </div>
      </div>
      <div class="row">
        <div class="input-field col s12 pad20">
            <input id="telephone" name="PHONE" type="tel" class="validate">
            <label for="PHONE" class="standard_font_estimate">Telephone</label>
            <div id="telephone_e" style="color:red;"></div>
        </div>
      </div>
      <div class="row">
        <div class="input-field col s12">
          <textarea id="textarea1" name="NEWUNIQUE" class="materialize-textarea"></textarea>
          <label for="NEWUNIQUE" class="standard_font_estimate">How can we help you?</label>
        </div>
      </div>
      <button class="btn waves-effect waves-light" type="button" id="emailLink" name="action">Submit
        <i class="mdi-content-send right"></i>
      </button>
    </form>
   
  </div>
  <script src="https://code.jquery.com/jquery-2.1.1.min.js"></script>
  <script type="text/javascript">
    //$(document).ready(function() {
      //$('select').material_select();
    //});
    $(function () {
      $('#emailLink').on('click', function (event) {
        event.preventDefault();
        //var email1 = 'aaron@kodeplay.com';
        //var subject = 'Request Estimate';
        first_name = $('#first_name').val();
        email = $('#email').val();
        telephone = $('#telephone').val();
        
        $('#first_name_e').html('');
        $('#email_e').html('');
        $('#telephone_e').html('');
        $('#first_name').css({"border-bottom" : "1px solid #9e9e9e", "border-shadow" : "0 0 0 0 solid #9e9e9e"});
        $('#email').css({"border-bottom" : "1px solid #9e9e9e", "border-shadow" : "0 0 0 0 solid #9e9e9e"});
        $('#telephone').css({"border-bottom" : "1px solid #9e9e9e", "border-shadow" : "0 0 0 0 solid #9e9e9e"});
        if(first_name == ''){
          $('#first_name').css({"border-bottom" : "1px solid red", "border-shadow" : "0 1px 0 0 solid red"});
          $('#first_name_e').html('Please Enter Full Name');
          return false;
        }
        if(email == ''){
          $('#email').css({"border-bottom" : "1px solid red", "border-shadow" : "0 1px 0 0 solid red"});
          $('#email_e').html('Please Enter Email');
          return false;
        }
        email_val = validateEmail(email);
        if(email_val === false){
          $('#email').css({"border-bottom" : "1px solid red", "border-shadow" : "0 1px 0 0 solid red"});
          $('#email_e').html('Please Enter valid Email');
          return false;
        }
        if(telephone == ''){
          $('#telephone').css({"border-bottom" : "1px solid red", "border-shadow" : "0 1px 0 0 solid red"});
          $('#telephone_e').html('Please Enter Telephone Number');
          return false;
        }
        var phoneNum = telephone.replace(/[^\d]/g, '');
        if(phoneNum.length >= 10 && phoneNum.length < 12) {  
        } else {
          $('#telephone').css({"border-bottom" : "1px solid red", "border-shadow" : "0 1px 0 0 solid red"});
          $('#telephone_e').html('Please Enter valid Telephone Number');
          return false;
        }
        $('#form').submit();
        //body_content = 'Name : ' + first_name + '%0D%0A';
        //body_content += 'Email : ' + email + '%0D%0A';
        //body_content += 'Phone : ' + telephone + '%0D%0A';
        //body_content += 'Explain us about this product or service : ' + textarea1 + '%0D%0A';
        //body_content += 'who are your users ? which new job will they be able to do when you launch ? : ' + textarea2 + '%0D%0A';
        //body_content += 'What is new and unique about this product or service ? what is your unique selling proposition and which advantage do you have over your competition ? : ' + textarea3 + '%0D%0A';
        //body_content += 'Estimated project time/cost : ' + estimate_time + '%0D%0A';
        //body_content += 'How did you hear about Kodeplay ? : ' + text1 + '%0D%0A';
        //body_content += 'Your timezone : ' + text2 + '%0D%0A';
        //var emailBody = body_content;
        //var emailBody = 'Some blah%0D%0ASome blah';
        //window.location = 'mailto:' + email1 + '?subject=' + subject + '&body=' +   emailBody;
      });
    });
    function validateEmail(email) {
      var re = /^([\w-]+(?:\.[\w-]+)*)@((?:[\w-]+\.)*\w[\w-]{0,66})\.([a-z]{2,6}(?:\.[a-z]{2})?)$/i;
      return re.test(email);
    }
    function phonenumber(inputtxt){  
      var phoneno = /^\d{10}$/;  
      if(inputtxt.value.match(phoneno)){  
        return true;  
      } else {  
        return false;  
      }  
    }
  </script>
