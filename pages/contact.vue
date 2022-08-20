<template>
<div  class="container content">
  <div>
        <!--Add few elements to the form-->
      <form ref="form" @submit.prevent="sendEmail">
      <div class="classes classes1">
        <HeaderInput />
      </div>
        
        <div class="classes classes1">
            <input type="email" name="user_email" class="name" placeholder="Enter your @email address" required/>
        </div>
        
        <div class="classes classes1">
            <textarea id="msg" name="message" placeholder="Write some message ..." style="height:100px" required></textarea>
        </div>

        <!--Add a button to save the data.-->
        <div class="classes classes1">
            <input type="submit" id="bt" value="Send">
        </div>
        <div class="classes" id="cs1">
          <div class="addup">
          <div>
            <label for="userId">Email:</label>
            <span> workflowmikedev@gmail.com</span>
            <label for="userId">Mobile N<span style="text-decoration: underline; color: purple;">o</span>:</label>
            <span> 09048356702 </span>
            <p class="mk"><a target="_blank" href="https://www.facebook.com/profile.php?id=100059001940097"><img class="wf" src="./images/facebook2 logo.png" alt="facebook"></a>
            <a target="_blank" href="https://www.instagram.com/crystalartzs/"><img class="wf" src="./images/instagram logo.png" alt="instagram"></a>
            <a target="_blank" href="https://twitter.com/Michael81289078?t=PxhXLmAihvR5fvSZBo4DSA&s=09"><img class="wf" src="./images/twitter2 logo.png" alt="instagram"></a>
            <a href="https://github.com/MICHAEL2JOSEPH"><img class="wf" src="./images/github logo.png" alt="instagram"></a>
            <a target="_blank" href="https://www.linkedin.com/in/michael-joseph-838498243"><img class="wf" src="./images/linkedin2 logo.png" alt="instagram"></a>
            </p>
            </div>
          </div>
          </div>
        </form>
        <footer><span>Copyright &copy; 2022</span></footer>
      </div>
    </div>
</template>

<script>

import emailjs from '@emailjs/browser';

export default {
    methods: {
    sendEmail() {
      emailjs.sendForm('service_4rqhl94', 'template_f4cn1cj', this.$refs.form, 'GSYzkqEmk8nQoMESZ')
        .then((result) => {
          alert("Message sent successfully✔")
            console.log('SUCCESS!', result.text);
        }, (error) => {
            alert("Message not sent❌, this could be due to poor or no internet connection.")
            console.log('FAILED...', error.text);
        });
    },
    // cannotbeempty() {
    //   const name = document.getElementById("name_error");
    //   if(name == "") {
    //     alert("Name cannot be empty")
    //   }
    // }
  }
}
</script>

<style>

* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}

.container {
  padding-top: 8%;
  width: 100%;
  align-items: center;
  display: flex;
  justify-content: center;
}

span {
  color: whitesmoke;
}

label {
  color: black;
}

.mk {
    display: inline-block;
    justify-content: space-around;
}

.wf {
    width: 40px;
    padding-left: 2%;
}

#cs1 {
  margin-bottom: 30px;
}

.addup {
  display: inline-block;
}


div .classes {
  padding: 10px;
  background: linear-gradient(135deg, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0));
  backdrop-filter: blur(20px);
  box-shadow: 0 8px 32px 0 rgba(0, 0, 0, 0.37);
  border: 1px solid rgba(255, 255, 255, 0.18);
  overflow: hidden;
}

      input[type=email], 
        textarea,
        select {
            width: 100%;
            height: auto;
            padding: 12px;
            border: none;
            border-radius: 8px;
            outline: none;
        }

        .class {
          width: 100%;
          padding: 12px;
          border: none;
          border-radius: 8px;
          outline: none;
        }
/* 
        input[type=text] {
          width: 100%;
            height: auto;
            padding: 12px;
            border: none;
            border-radius: 8px;
            outline: none;
        } */

        .mood {
            padding: 10px;
            background: linear-gradient(135deg, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0));
            backdrop-filter: blur(20px);
            box-shadow: 0 8px 32px 0 rgba(0, 0, 0, 0.37);
            border: 1px solid rgba(255, 255, 255, 0.18);
            overflow: hidden;
        }
        
        input[type=submit] {
            width: 150px;
            float: right;
            cursor: pointer;
            padding: 7px;
            border: none;
            border-radius: 8px;
            color: white;
            background-image: linear-gradient(to right, #cc2b5e, #753a88);
        }
::-webkit-scrollbar{width:1px;border-left:1px solid #48a2d6;}
::-webkit-scrollbar-thumb{background-color: transparent;}

@media only screen and (max-width: 575px) {
        input[type=submit] {
            width: 150px;
            float: right;
            cursor: pointer;
            padding: 7px;
            border: none;
            border-radius: 8px;
            color: white;
            background-image: linear-gradient(to right,#08043b, #48a2d6);
        }

        .wf {
            width: 40px;
            padding-left: 15px;
        }

        .content {
          width: 100%;
          height: 100%;
          padding-top: 10%;
        }
}
</style>